## wikishop
Обучение модели классифицировать текстовые комментарии на позитивные и негативные. В нашем распоряжении набор данных с разметкой о токсичности текстов.  
Решить задачу можно как с помощью BERT, так и без этой нейронки.  
Метрика `F1` на тестовой выборке должна быть не менее 0.75.  

# Проект для «Викишоп»  

*Проект выполнен в трёх вариантах*

**Папка `wikishop_manual`**  
Данный проект был выполнен сначала с ручным сэмплированием данных и ручным перебором моделей и их гиперпараметров. Код получился длинным, но все действия выполнены подробно, пошагово. Написаны функции для подготовки данных и обучения моделей. Модели обучались на сэмлированных данных и на несэмплированных данных, с разными гиперпараметрами, модели настраивались на валидационной выборке. Измерялось время работы каждой модели. Нужное качество модели на тестовой выборке получено. Выбрана модель с лучшим качеством и наиболее высокой скоростью работы.  

**Папка `wikishop_pipe`**
Позже проект был выполнен заново, с использованием пайплайна. Код получился компактным. Валидационная выборка не создавалась, а использовался валидатор. Качество модели получено более высокое.  

**Папка `wikishop_bert`**  
Кроме того, решено было попробовать использовать нейронку `BERT`, с помощью которой выполнить подготовку текстов к обучению моделей. Из-за недостатка вычислительных мощностей было выбрано 10000 случайных текстов, которые подготовили с использованием `BERT`, затем в пайплайне обучены несколько моделей. Качество лучшей модели оказалось низким. То есть 10000 текстов недостаточно для получения успешной модели МО.