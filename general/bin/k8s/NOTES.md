# Заметки в процессе анализа 

* поле kubernetes_id в сущности seaf.ta.components.k8s_deployment
    Данное поле кажется избыточным, т.к. задаёт дополнительную связь относительно связи
    с сущностью namespace. Аналитика должна строиться отдельно от модели ORM
    Более того, в сущности - это массив из кластеров, не очень понятно, при каких условиях можно как-то связать между собой деплойменты в разных кластерах
* выгрузка объектов типа POD
    Выгрузка данных объектов кажется бессмысленной
* поле availabilityzone_id не имеет смысла в сущности deployment
* поле maxunavailable в deployment действительно только для стратегии RollingUpdate, но почему-то находится в списке обязательных полей
* поле k8s_pods в deployment не имеет смысла, см. выгрузка объектов типа POD
* контейнеры в deployment описаны в виде шаблонов и не являются сильными сущностями, ссылки на них сделать не получится.
    смысла выгружать запущенные контейнеры нет, так же, как и запущенные PODы