---
title: "Managed Service for Elasticsearch. Ответы на вопросы"
description: "Как получить логи моей работы в управляемом сервисе Elasticsearch?  Ответы на этот и другие вопросы в данной статье."
---

# Вопросы и ответы о {{ mes-short-name }}

## Общие вопросы {#general}

#### Как происходит обслуживание кластеров {{ ES }}? {#service-window}

Под обслуживанием в {{ mes-short-name }} понимается:

* автоматическая установка обновлений и исправлений {{ ES }} для ваших хостов;
* изменение класса хостов и объема хранилища;
* другие сервисные работы {{ mes-short-name }}.


#### Какую версию {{ ES }} использует {{ mes-short-name }}? {#dbms-version}

В {{ mes-short-name }} доступны версии {{ ES }}, поддерживаемые производителем. Подробнее см. в разделе [{#T}](../concepts/update-policy.md).


#### Что происходит, когда выпускается новая версия {{ ES }}? {#new-version}

При выходе новых версий, содержащих только исправления ошибок (_maintenance release_), программное обеспечение кластеров автоматически обновляется после короткого периода тестирования.

Владельцы затронутых кластеров БД получают предварительное оповещение о сроках проведения работ и доступности баз данных.


#### Что происходит, когда версия {{ ES }} становится неподдерживаемой {#dbms-deprecated}

{{ mes-short-name }} автоматически оповещает владельцев кластеров о том, что срок поддержки используемой версии {{ ES }} истекает, по электронной почте.

Кластеры с неподдерживаемой версией {{ ES }} обновляются в соответствии с [политикой управления версиями](../concepts/update-policy.md).

Владельцы затронутых кластеров получают предварительное оповещение о сроках проведения работ и доступности баз данных.

{% include [qa-logs.md](../../_includes/qa-logs.md) %}