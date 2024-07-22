# Проект для Викишоп

## Задание
Интернет-магазин «Викишоп» запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.

Обучите модель классифицировать комментарии на позитивные и негативные. В вашем распоряжении набор данных с разметкой о токсичности правок.

Постройте модель со значением метрики качества F1 не меньше 0.75.

## Описание данных
Данные находятся в файле toxic_comments.csv. Столбец text в нём содержит текст комментария, а toxic — целевой признак.

## Ход работы
1. Загрузили и проверили данные. Выявилась проблема дисбаланса классов. Есть два пути решения:
- сэмплировать тренировочную выборку,
- указать при обучении моделей, что нужно обратить внимание на баланс классов
2. Выполнили очистку и лемматизацию текстов.
3. Разделили данные на тренировочную, валидационную и тестовую выборки.
4. Выполнили сэмплирование данных.
5. Подготовили данные, получили признаки в векторном представлении.
6. Обучили несколько моделей:
- логистическую регрессию,
- дерево решений,
- случайный лес,
- бустинговую модель LGBM,
- бустинговую модель CatBoost
7. Для каждой модели попробовали подобрать гиперпараметры, а также использовали и сэмплированные, и несэмплированных данные.
8. Выявили, какая модель, с какими гиперпараметрами и на каких данных показала лучший результат. Использовали метрику F1.
9. Дали рекомендацию заказчику, какую модель лучше использовать для определения токсичности комментариев.