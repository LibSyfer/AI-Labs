# lab2. Реализация алгоритма kNN


## 1. Мотивация

Данная лабораторная работа нацелена на изучение алгоритма kNN.


В результате выполнения данной лабораторной работы студент получит следующие навыки:

	- написание кода на Python
	- обучение простой модели машинного обучения
	- анализ результатов

_______________________________________________________________________________________________________________


## 2. Алгоритм выполнения

В рамках данного блока необходимо проделать следующие шаги:

1. С использованием инструментов Jupyter создать и перейти в папку `labs0/lab2`.
2. Внутри создать jupyter notebook с названием: `knn.ipynb`
3. Создать папку `data` 
4. Достать данные из архива и положить в папку `data` файлы `student_exam_data.csv` 
5. Открыть созданный notebook на шаге 2.
6. Заполнить notebook по требованиям представленным ниже.

#### Требования к заданию, которое должно быть сделано в Jupyter Notebook

1. С использованием pandas прочитать данные. У вас есть один набор данных в формате CSV, содержащих информацию о экзаменах студетов. 

Данные включают следующую информацию:

	Результаты сдачи экзаменов
	- `Study Hours` - Количество часов изучения
	- `Previous Exam Score` - Оценка за предыдущий экзамен
	- `Pass/Fail` - Успехи или не успех сдачи экзамена

2. Взять в качестве шаблона следующий код и заполнить недостающие пробелы в методах.

```
import numpy as np
import pandas as pd


class kNNClassifier:
    """
    Классификатор на основе k-ближайших соседей (kNN).
    
    Параметры
    -----------
    k : int
        Количество ближайших соседей для учета при классификации.
    
    Attributes
    -----------
    k : int
        Количество ближайших соседей.
    X_train : numpy array, shape (n_samples, n_features)
        Обучающие векторы.
    y_train : numpy array, shape (n_samples,)
        Целевые значения для обучающих векторов.

    """
    
    def __init__(self, k=1):
        # Здесь должен быть ваш код

    def fit(self, X_train, y_train):
        """Обучает модель на обучающих данных.
        
        Параметры
        -----------
        X_train : numpy array, shape (n_samples, n_features)
            Обучающие векторы.
        y_train : numpy array, shape (n_samples,)
            Целевые значения для обучающих векторов.
        
        Возвращает
        -----------
        self : object
        """
        # Здесь должен быть ваш код

    def predict(self, X_test):
        """Классифицирует тестовые данные на основе kNN.
        
        Параметры
        -----------
        X_test : numpy array, shape (n_samples, n_features)
            Тестовые векторы.
        
        Возвращает
        -----------
        predictions : numpy array, shape (n_samples,)
            Предсказанные метки классов для тестовых векторов.
        """
        # Здесь должен быть ваш код

    def _predict_single(self, x):
        """Классифицирует одиночный тестовый вектор."""
        # Здесь должен быть ваш код
```


3. Импортировать kNNClassifier из библиотеки sklearn и сравнить его работу со своей реализацией модели.

```
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

k = 10

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Ваша реализация
knn_model_custom = kNNClassifier(k)
knn_model_custom.fit(X_train, y_train)

# Реализация в kNN
knn_model_sklearn = KNeighborsClassifier(n_neighbors=k)
knn_model_sklearn.fit(X_train, y_train)

y_pred_custom = knn_model_custom.predict(X_test)
y_pred_sklearn = knn_model_sklearn.predict(X_test)


accuracy_custom = accuracy_score(y_test, y_pred_custom)
accuracy_sklearn = accuracy_score(y_test, y_pred_sklearn)

print(f"Accuracy для собственного kNN: {accuracy_custom}")
print(f"Accuracy для scikit-learn kNN : {accuracy_sklearn}")
print(accuracy_custom == accuracy_sklearn)

```

4. В результате accuracy_custom должно быть равно accuracy_sklearn. Добиться этого и защитить работу у преподавателя.













