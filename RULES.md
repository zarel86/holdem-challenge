# Регламент проведения Sberbank Holdem Challenge

## Общие правила игры

- В каждой игре принимают участие 9 случайно выбранных ботов.
- Симулятор игры запускается сразу после запуска всех ботов.
- Игроки получают начальное число фишек `initial_stack`, фиксируется размер малого блайнда `small_blind_amount`.
- На каждый ход боту дается определенное количество времени `time_limit_action` (например, 0.2 секунды). Время на ход начинает отсчитываться от момента, когда симулятор запросил у бота действие.
- У каждого бота есть банк дополнительного времени в размере `time_limit_bank`. В случае, если бот не укладывается в отведенное на ход время, то начинает расходоваться время из банка.
- В случае, если у бота заканчивается время на ход и заканчивается банк дополнительного времени, то бот принудительно прекращает свою работу и считается “упавшим” (failed).
- В случае, если бот преждевременно прекращает свою работу, либо дает ответ в неверном формате, то он считается “упавшим” и отстраняется от игры.
- Упавшие (failed) боты остаются в игре, но симулятор делает за них автоматический сброс карт.
- Игра завершается, когда достигается максимальное число сыгранных раундов `max_round`, либо когда остается только один участник с фишками.

## Он-лайн этап

Он-лайн этап Sberbank Holdem Challenge проводится для того, чтобы участники имели возможность разобраться с интерфейсом до основной части соревнования, сделали свои первые стратегии. Кроме того, в конце он-лайн этапа происходит большой отборочный турнир, по итогам которого лучшие участники получают приглашения на основной офф-лайн этап.

#### Отправка бота в систему

- На ежедневный турнир от каждого участника выбирается самый последний бот (на момент запуска турнира), среди отправленных и успешно прошедших проверку в тестирующей системе.
- Проверка в тестирующей системе проводится следующим образом: бот участника играет 10 игр с рандомными ботами (делающими случайные действия из доступных). Проверка считается успешно пройденной, если бот участника успешно завершил все 10 игр и не упал.
Ежедневные турниры
- Во время он-лайн этапа проводятся ежедневные турниры, которые стартуют в полночь 00:00 МСК.
- В турнире участвует по одному боту от каждого участника, выбирается последний успешный из отправленных в систему на момент начала турнира.
- Боты всех участников играют приблизительно одинаковое число игр, но не менее 30 игр для каждого из участников.
- После окончания турнира участникам становится доступна таблица результатов с указанием основного показателя качества игры — среднее число фишек, оставшееся к концу игры по итогам всех игр в турнире. Кроме того, участники получают доступ к архиву с реплеями всех игр турнира.
- Параметры игры на ежедневном турнире:
  - max_round = 50 (максимальное число раундов)
  - initial_stack = 1500 (начальное число фишек)
  - small_blind_amount = 15 (размер малого блайнда)
  - time_limit_bank = 30 сек (размер банка времени)
  - time_limit_action = 0.2 сек (время на ход)

#### Отборочный турнир

- Он-лайн этап завершается отборочным турниром, который начинается 18 сентября (понедельник), в 03:00 МСК. С этого момента прием решений в систему прекращается.
- В отборочном турнире участвует по одному боту от каждого участника, выбирается последний успешный из отправленных в систему на момент начала турнира.
- Боты всех участников играют приблизительно одинаковое число игр, но не менее 60 игр для каждого из участников.
- Параметры игры на отборочном турнире совпадают с параметрами ежедневного турнира.
- После окончания турнира формируется рейтинг участников по убыванию среднего числа фишек, оставшихся у бота к концу игры, по итогам всех игр турнира.
- Участники приглашаются на основной этап по рейтингу. Участники, более высокие по рейтингу имеют более высокий приоритет в приглашении.

## Основной этап (офф-лайн)

Основной этап Sberbank Holdem Challenge проводится в формате хакатона на базе Корпоративного Университета Сбербанка 23 и 24 сентября.

- Во время основного этапа участники имеют возможность разрабатывать и отправлять своих ботов в систему.
- Игры между ботами случайных участников проводятся непрерывно.
- Сразу после завершения игры, участникам становится доступен реплей игры. Реплеи всех игр можно использовать во время основного этапа для анализа стратегий других участников, улучшения собственной стратегии.
- В конце основного этапа будет проведен большой турнир, который подведет итоги и выявит три лучшие стратегии, авторы которых получат призы. Схема проведения основного этапа будет объявлена заранее, но после подведения итогов он-лайн этапа. 