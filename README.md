# Оптимизация политики по ограничению COVID-19 контактов в Москве

С 26 марта людям старше 65 нельзя выходить на улицу. За это им заплатят небольшие деньги. И это хорошо. Но одновременно это траты бюджета, которые можно оптимизировать, если взглянуть на данные: вводить меры в отношении не всех пенсионеров, а только тех, кому это необходимо, чтобы остаться дома (например одиноким или незанятым, проживающих в определенных районах). Сэкономленные деньги можно потратить на что-то еще в связи с эпидемией, либо не вводить новые налоги, любо легче принимать решения о проведении повторных мер, меру можно сделать доступной в регионах с маленькими бюджетами.

## Подробнее

Оперативный штаб Москвы, руководствуясь указом Мэра от 23 марта (№ 26-УМ), осуществляет меру по самоизоляции граждан в возрасте выше 65, обещая выплатить 2000 рублей тем, кто соблюдали карантин в период с 26 по 14 апреля. Для таких пороговых мер есть возможность оценить их эффективность. Если посчитать количество граждан в возрасте 65, которые были замечены на улице и лишины выплаты, а также лиц в возрасте 64 лет, которые были замечены на улице, на которых не распространяется мера, то разница между этими двумя числами дает хорошую оценку количества людей, которые остались дома именно из-за того, что им обещали выплату. Такой метод используют во всем мире для оценки государственной политики: например Angrist, J. D., & Lavy, V. (1999)

Вот так такой анализ может выглядеть (в рамках этой демонстрации использованы симулированные данные):

![Regression Discontinuity](/regression_discontinuity.png)

Используя демографическую информацию, также можно давать рекомендации по улучшению политики. Простой пример: предположим бюджет в среднем тратит на занятого в госсекторе пенсионера 500 рублей и снижает его вероятность появиться на улице на 10 процентных пунктов, а на занятого в частном секторе пенсионера 2000 рублей и снижает его верояность появиться на улице на 20 процентных пунктов. В таком случае эффективно в выплатах приоретизировать госслужащих (10/500 > 20/2000). Конечно, чем больше демографической информации есть, тем лучше получается итоговая политика. Такой поход называется Policy learning и продвинутом варианте использует среди прочего методы машинного обучения (чаще всего леса с градиентным бустингом). Методы описаны в работах: Athey, S., & Wager, S. (2017), Zhou, Z., Athey, S., & Wager, S. (2018)

Вот примеры, как может выглядеть такой анализ (в рамках этой демонстрации использованы симулированные данные):

![Uplift](/uplift.png)

2000 рублей на человека никогда не тратится из-за нарушений карантина. По картинке видно, что осуществляя взвешенную политику можно без потери в эффекте сэкономить бюджет с 1600 рублей  в расчете на пенсионера до 1200. При бюджете в 800 рублей мы можем сохранить почти весь эффект и это лучше, чем наивное случайное правило в 2 раза. Также можно рассматривать эффектиные меры при низком бюджете, как в регионах (например 400 рублей в расчете на пенсионера)

Исследователь может соблюсти ограничения на социальную приемлемость политики, которая не должна дискриминировать по полу, поощрять скорее социально незащищенные слои населения. Методы по соблюдению таких ограничений описаны в работе Athey, S., & Wager, S. (2017). В результате получается интерпретируемое понятное правило вроде такого (взято из работы Athey в контексте грантов на обучение)

![decision_tree](/decision_tree.png)

Имея в руках данные мы можем подходить к таким вопросам: при ограниченном бюджете, кого эффективнее стимулировать денежно -- одиноких пенсионеров? незанятых пенсионеров? пенсионеров с инвалидностью?

## Литература

1. Athey, S., & Wager, S. (2017). Efficient policy learning. arXiv preprint arXiv:1702.02896.
2. Angrist, J. D., & Lavy, V. (1999). Using Maimonides' rule to estimate the effect of class size on scholastic achievement. The Quarterly journal of economics, 114(2), 533-575.
3. Zhou, Z., Athey, S., & Wager, S. (2018). Offline multi-action policy learning: Generalization and optimization. arXiv preprint arXiv:1810.04778.

 ## Контакты
 
 Если вас заинтересовала эта симуляция, я буду рад пообщаться и ответить на вопросы по адресу go9513@gmail.com
