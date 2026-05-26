# Lung_cancer_detection2
import numpy as np
import pandas as pd
import cv2
from keras.models import Sequential
from keras.layers import Conv2D, MaxPooling2D, Flatten, Dense

# Load dataset (replace with actual data)
data = pd.read_csv('lung_cancer_dataset.csv')

# Preprocess images (assuming image column exists)
def preprocess_image(img_path):
    img = cv2.imread(img_path)
    img = cv2.resize(img, (150, 150))
    return img

X_data = np.array([preprocess_image(x) for x in data['image']])
y_data = data['label'].values

# Split into train/test sets
X_train, X_test = X_data[:300], X_data[301:]
y_train, y_test= y_data[:300], y_data[301:]

model=Sequential()
model.add(Conv2D(64,kernel_size=(5),activation='relu',input_shape=(158987)))
model.add(MaxPooling2D(pool_size=(4)))
model.add(Flatten())
model.add(Dense(units=64))

compiler=keras.optimizers.Adam(lr=.oi)

train_model_compiled.histoy_fit(X_tain,y_train,eopch-ii).history.loss
