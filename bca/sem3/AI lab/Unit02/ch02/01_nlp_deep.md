## **10.Using python NLTK, perform the following Natural Language Processing tasks for text content.**

1) **Tokenizing.**  
2) **Filtering stop words.**  
3) **Stemming.**  
4) **POS tagging.**  
5) **Chunking.**  
6) **Named-Entity Recognition(NER).**

```
import nltk
from nltk.tokenize import sent_tokenize, word_tokenize
from nltk.corpus import stopwords
from nltk.stem import PorterStemmer
from nltk.chunk import RegexpParser

text = "This is a University"

sentences = sent_tokenize(text)

words = [word_tokenize(s) for s in sentences]

stop_words = set(stopwords.words('english'))
words_no_stop = [[w for w in s if w.lower() not in stop_words] for s in words]

stemmer = PorterStemmer()
stems = [[stemmer.stem(w.lower()) for w in s] for s in words_no_stop]

pos = [nltk.pos_tag(s) for s in words]

chunker = RegexpParser("""
    NP: {<DT>?<JJ>*<NN>}
    VP: {<VB.><NP|PP|CLAUSE>}
""")

chunks = [chunker.parse(p) for p in pos]

ner = [nltk.ne_chunk(p) for p in pos]

print("Sentences:", sentences)
print("Words:", words)
print("Words (no stopwords):", words_no_stop)
print("Stems:", stems)
print("POS Tags:", pos)
print("Noun Phrase Chunks:", chunks)
print("Named Entities:", ner)
```

### **Output:**

- **Sentences:\[‘This is a Uiversity’\]**
**\> Sentences:1**

- **First sentence tokens:\[‘This’, ’is’, ’a’, ’university’\]**

- **Filtered words(no stop):\[‘university’\]**

- **Stems(porter):\[‘univers’\]**

- **POS tags(first 12):\[(‘This’, ‘DT’),(‘is’, ‘VBZ’),(‘a’,**
**‘DT’),(‘university’, ‘NN’)\]**

- **Noun phrase chunks(sentence 1):\[Tree(‘S’, \[(‘This’, ‘DT’), (‘is’, ‘**  

             **‘VBZ’), (‘a’, ‘DT’), (‘university’, ‘NN’)\])\])\]**

- **Named entities (Sentence 1): \[Tree(‘S’, \[(‘This’, ‘DT’), (‘is’,**  

                            **‘VBZ’), (‘a’, ‘DT’), ( ‘university’, ‘NN’)\])\]**


## **11.Perform Image classification for a given dataset using CNN. You may use Tensorflow/Keras.**

```
import numpy as np
import matplotlib.pyplot as plt
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras import layers, models
from sklearn.metrics import confusion_matrix, classification_report

SEED = 42
np.random.seed(SEED)
tf.random.set_seed(SEED)
plt.rcParams['figure.figsize']=(8,5)

(x_train, y_train), (x_test, y_test) = keras.datasets.cifar10.load_data()

print("Raw shapes:")
print("x_train:", x_train.shape, " y_train:", y_train.shape)
print("x_test: ", x_test.shape, " y_test: ", y_test.shape)

class_names = ['airplane','automobile','bird','cat',
               'deer','dog','frog','horse','ship','truck']


def show_samples(X, Y, class_names, rows=4, cols=4):
    fig, axes = plt.subplots(rows, cols, figsize=(cols*2, rows*2))
    indices = np.random.choice(len(X), rows*cols, replace=False)
    for ax, idx in zip(axes.flatten(), indices):
        ax.imshow(X[idx])
        ax.set_title(class_names[Y[idx][0]])
        ax.axis("off")
    plt.tight_layout()
    plt.show()

show_samples(x_train, y_train, class_names)

IMG_SIZE=(32,32)
BATCH_SIZE=64
AUTOTUNE=tf.data.AUTOTUNE

x_train = x_train.astype("float32") / 255.0
x_test = x_test.astype("float32") / 255.0

train_ds = tf.data.Dataset.from_tensor_slices((x_train, y_train.reshape(-1,))) 
train_ds = train_ds.shuffle(10000, seed=SEED).batch(BATCH_SIZE).prefetch(AUTOTUNE)

test_ds = tf.data.Dataset.from_tensor_slices((x_test, y_test.reshape(-1,))) 
test_ds = test_ds.batch(BATCH_SIZE).prefetch(AUTOTUNE)

def make_small_cnn(input_shape=(32,32,3), num_classes=10):
    inputs = keras.Input(shape=input_shape)

    x = layers.Conv2D(32, (3,3), activation='relu', padding='same')(inputs)
    x = layers.MaxPool2D((2,2))(x)

    x = layers.Conv2D(64, (3,3), activation='relu', padding='same')(x)
    x = layers.MaxPool2D((2,2))(x)

    x = layers.Conv2D(128, (3,3), activation='relu', padding='same')(x)
    x = layers.GlobalAveragePooling2D()(x)

    x = layers.Dropout(0.3)(x)
    outputs = layers.Dense(num_classes, activation='softmax')(x)

    model = keras.Model(inputs, outputs, name="small_cnn")
    return model

model = make_small_cnn()
model.summary()

model.compile(
    optimizer=keras.optimizers.Adam(),
    loss="sparse_categorical_crossentropy",
    metrics=["accuracy"]
)

callbacks = [ 
keras.callbacks.EarlyStopping(monitor='val_loss', patience=4, restore_best_weights=True), 
keras.callbacks.ModelCheckpoint("best_cifar10.h5", save_best_only=True) 
]

history = model.fit(
    x_train, y_train,
    validation_split=0.2,
    epochs=EPOCHS,
    batch_size=BATCH_SIZE
)

plt.figure(figsize=(12,4))
plt.subplot(1,2,1)
plt.plot(history.history["loss"], label="train_loss")
plt.plot(history.history["val_loss"], label="val_loss")
plt.legend()
plt.title("Loss")

plt.subplot(1,2,2)
plt.plot(history.history["accuracy"], label="train_acc")
plt.plot(history.history["val_accuracy"], label="val_acc")
plt.legend()
plt.title("Accuracy")
plt.show()

test_loss, test_acc = model.evaluate(test_ds)
print(f"Test loss: {test_loss:.4f}   Test accuracy: {test_acc:.4f}")

y_pred_probs = model.predict(x_test, batch_size=BATCH_SIZE) 
y_pred = np.argmax(y_pred_probs, axis=1) 
y_true = y_test.reshape(-1,)


cm = confusion_matrix(y_true, y_pred)  
plt.figure(figsize=(10,8)) 
cm_norm = cm.astype('float') / cm.sum(axis=1)[:, np.newaxis] 
sns.heatmap(cm_norm, annot=True, fmt=".2f", cmap='Blues', xticklabels=class_names, 
yticklabels=class_names) 
plt.xlabel('Predicted'); plt.ylabel('True'); plt.title('Normalized Confusion Matrix') 
plt.show()

print("Classification report (precision / recall / f1):\n") 
print(classification_report(y_true, y_pred, target_names=class_names, digits=3)) 
def show_predictions(X, y_true, y_pred, class_names, count=1): 
plt.figure(figsize=(12,6)) 
indices = np.random.choice(len(X), count, replace=False) 
for i, idx in enumerate(indices): 
plt.subplot(3, 4, i+1) 
plt.imshow(X[idx]) 
title = f"T:{class_names[y_true[idx]]}\nP:{class_names[y_pred[idx]]}" 
color = 'green' if y_true[idx] == y_pred[idx] else 'red' 
plt.title(title, color=color) 
plt.axis('off') 
plt.tight_layout() 
plt.show() 
show_predictions(x_test, y_true, y_pred, class_names, count=10)
```

### **Output 1:**
![Image 1](https://lh3.googleusercontent.com/d/180GCOVoO2Oc_VuKALCBq9mM1oOo2dqXm)
![Image 2](https://lh3.googleusercontent.com/d/1G_AIbszcPl_RNSjBRNP7ip8VbJXWGqCH)
![Image 3](https://lh3.googleusercontent.com/d/1B7gj7CEwKjsMrDnzscoQVO4AgRyE58Re)
![Image 4](https://lh3.googleusercontent.com/d/1Xp2bxDE55MINcWwQGnHT1clnWllp_LcZ)
![Image 5](https://lh3.googleusercontent.com/d/1P4gCn8G_sR9SbA-N4NFRuVICLBKkvZYv)
![Image 6](https://lh3.googleusercontent.com/d/1IL3zV1Xo-y_W2Gb5ZSd3NySN_UKtH52m)
