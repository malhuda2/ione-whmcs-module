# ione-whmcs-module
IONe based Provisioning Module for WHMCS

Перед началом не забудьте установить и настроить IONe Cloud на вашей OpenNebula. [Инструкция](https://docs.ione-cloud.net/).

## 1. Предварительная настройка WHMCS

### Добавьте хост с IONe в белый список
Путь в настройках: 

    Настройки -> 
      Общие настройки ->
        Безопасность ->
          Список IP с правом доступа к API

### Добавьте группу продуктов
Путь:

    Настройки ->
      Продукты/Услуги ->
        Создать новую группу

Затем создайте новый продукт, например 'Small VM'.

> **Важно!**
> Не забудьте заполнить поле **Описание продукта**

Пример заполненного поля:
```json
{
    "properties": [
        {
            "GROUP": "cpu_core",
            "VALUE": "1",
            "TITLE": "1"
        },
        {
            "GROUP": "ram",
            "VALUE": "1 Гб",
            "TITLE": "1 Gb"
        },
        {
            "GROUP": "hdd",
            "VALUE": "30 Гб",
            "TITLE": "30 Gb",
            "IOPS": "500"
        }
    ]
}
```

### Добавить дополнение к продукту
Путь:

    Настройки ->
      Продукты/Услуги ->
        Дополнения к продуктам

> **Важно!**
> Не забудьте заполнить поле **Описание продукта**

Пример заполненного поля:
```json
{
    "GROUP": "os",
    "TITLE": "CentOS x64",
    "VALUE": "1"
}
```
Отметьте чекбокс **Показывать при заказе**.

Это минимальные настройки для автоматического создания ВМ из заказов.