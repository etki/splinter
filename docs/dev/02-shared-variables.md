# Shared variables (общие переменные шаблонов)

К сожалению, Freemarker самостоятельно создает новый экземпляр фабрики, если не находят его в странных property
конфигурации, к которым я не смог получить доступ. Поэтому сделать всё красиво не получилось, и для простановки общих
переменных необходимо из инициализации `Server` пробиться к `SharedVariablesManager` (лежит в `SimpleContainer`) и
добавить произвольную переменную простым вызовом метода. Фабрика сама запросит этот экземпляр при инициализации и
проставит все находящиеся в нем на этот момент переменные.