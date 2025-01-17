# Настроить SLA для задач

SLA в {{ tracker-name }} — это [набор правил](manager/sla.md), который устанавливает временные рамки для обработки задач очереди. Например, вы можете задать время, за которое исполнитель должен отреагировать на новую задачу, ответить на комментарий заказчика или полностью закончить работу над задачей. Если исполнитель не уложится в срок, {{ tracker-name }} отправит вам уведомление об этом.

SLA можно использовать в работе службы поддержки, чтобы [контролировать скорость обработки обращений](support-process-sla.md).

Для каждого правила можно [настроить](manager/sla.md#section_n1s_42g_vdb):

* фильтр задач, к которым оно будет применяться; 

* условия запуска, приостановки и остановки таймера; 

* [график работы](manager/schedule.md) таймера.

При выполнении заданных условий запускается таймер. Таймер активен согласно графику работы. В нерабочие часы отсчет времени идти не будет.

Таймеры SLA во всех системных графиках не работают в праздничные дни, т.к. праздничные дни считаются нерабочими.

