При создании кластера вы можете выбирать между следующими типами хранилища:

* Стандартное сетевое хранилище (`network-hdd`) — самый экономичный вариант для кластеров, не требовательных к скорости записи и чтения.
* Быстрое сетевое хранилище (`network-ssd`) — компромиссный вариант: медленнее, чем локальное хранилище, но, в отличие от локальных дисков, обеспечивает сохранность данных при выходе из строя оборудования {{ yandex-cloud }}.
* Нереплицируемое сетевое хранилище (`network-ssd-nonreplicated`) — сетевое хранилище с повышенной производительностью, реализованной за счет устранения избыточности. Объем хранилища можно увеличивать только с шагом 93 ГБ.
* Быстрое локальное хранилище (`local-ssd`) — самые быстрые диски. Объем локального хранилища можно увеличивать только с шагом 100 ГБ.