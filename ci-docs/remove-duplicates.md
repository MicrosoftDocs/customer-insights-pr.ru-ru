---
title: Удаление повторяющихся данных перед объединением
description: Вторым шагом в процессе объединения является выбор записи, которую необходимо сохранить при обнаружении повторяющихся данных.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741668"
---
# <a name="remove-duplicates-before-unifying-data"></a>Удаление повторяющихся данных перед объединением

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Этот шаг процесса объединения дополнительно позволяет настроить правила для обработки повторяющихся записей внутри сущности. *Дедупликация* выявляет повторяющиеся записи и объединяет их в одну запись. Исходные записи связываются с объединенной записью с альтернативными идентификаторами. Если правила не настроены, применяются системные правила.

## <a name="include-enriched-entities-preview"></a>Включение обогащенных сущностей (предварительная версия)

Если вы обогатили сущности на уровне источника данных, выберите их, чтобы улучшить результаты объединения. Дополнительная информация дана в теме [Обогащение источников данных](data-sources-enrichment.md).

1. На странице **Повторяющиеся записи** нажмите **Использовать обогащенные сущности** в верхней части страницы.

1. В области **Использовать обогащенные сущности** выберите одну или несколько обогащенных сущностей.

1. Нажмите кнопку **Готово**.

## <a name="define-deduplication-rules"></a>Определение правил дедупликации

1. На странице **Повторяющиеся записи** выберите сущность и нажмите **Добавить правило** для определения правил дедупликации.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Снимок экрана страницы повторяющихся записей с выделенным пунктом «Показать больше»":::

   1. В области **Добавить правило** ведите следующие данные:
      - **Выбрать поле**: выберите из списка доступных полей сущность, которую вы хотите проверить на наличие повторяющихся данных. Выберите поля, которые, вероятно, уникальны для каждого клиента. Например, адрес электронной почты или комбинация имени, города и номера телефона.
      - **Нормализация**: выберите из следующих вариантов нормализации для выбранных атрибутов.
        - **Числительные**: преобразует другие числовые системы, например римские цифры, в арабские. *VIII* становится *8*.
        - **Символы**: удаляет все символы и специальные знаки. *Head&Shoulder* становится *HeadShoulder*.
        - **Текст в нижний регистр: переводит все символы в нижний регистр.** *ВСЕ ЗАГЛАВНЫЕ БУКВЫ и Капитализация Начальных Букв* становится *все заглавные буквы и капитализация начальных Букв*.
        - **Тип (телефон, имя, адрес, организация)**: стандартизирует имена, должности, номера телефонов, адреса и т. д.
        - **Unicode в ASCII**: преобразует обозначение Unicode в символы ASCII. */u00B2* становится *2*.
        - **Пробел**: удаляет все пробелы. *Hello   World* становится *HelloWorld*.
      - **Точность**: установите уровень точности, чтобы иметь доступ к этому условию.
        - **Базовый**: выберите *Низкий (30%)*, *Средний (60%)*, *Высокий (80%)*, и *Точный (100%)*. Выберите **Точно**, чтобы сопоставлять только записи, которые совпадают на 100 процентов.
        - **Пользовательский**: задайте процент, которому должны соответствовать записи. Система будет сопоставлять только записи, превышающие этот порог.
      - **Имя**: имя для правила.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Снимок экрана области добавления правила для удаления повторяющихся данных.":::

   1. При желании выберите **Добавить** > **Добавить условие**, чтобы добавить дополнительные условия к правилу. Условия связаны с помощью логического оператора "И", поэтому выполнение происходит только при соблюдении всех условий.

   1. Также можно выбрать **Добавить** > **Добавить исключение**, чтобы [добавить исключения в правило](match-entities.md#add-exceptions-to-a-rule). Исключения используются для устранения редких случаев ложноположительных и ложноотрицательных результатов.

   1. Нажмите **Готово**, чтобы создать правило.

1. Вы также можете (необязательно) [добавить дополнительные правила](#define-deduplication-rules).

1. Выберите сущность, а затем нажмите **Изменить настройки объединения**.

1. В области **Объединить настройки**:
   1. Выберите один из трех вариантов, чтобы определить, какую запись сохранить при обнаружении повторяющихся данных:
      - **Наиболее заполненные**: определяет запись с наиболее заполненными полями атрибутов в качестве записи победителя. Это параметр объединения по умолчанию.
      - **Самые новые**: определяет запись победителя на основе "самая новая". Требуется дата или числовое поле для определения давности.
      - **Наименее недавние**: определяет запись победителя на основе "наименее недавние". Требуется дата или числовое поле для определения давности.
      
      В случае ничьей побеждает запись с MAX(PK) или большим значением первичного ключа.
      
   1. Также можно определить параметры объединения для отдельных атрибутов сущности. Для этого выберите **Расширенные** в нижней части области. Например, вы можете сохранить самую последнюю электронную почту И наиболее полный адрес из разных записей. Разверните сущность, чтобы увидеть все ее атрибуты, и определите, какой параметр использовать для отдельных атрибутов. Если вы выберете вариант, основанный на давности, вам также необходимо указать поле даты/времени, определяющее давность.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Область расширенных настроек объединения, показывающая последние сообщения электронной почты и полный адрес":::

   1. Выберите **Готово**, чтобы применить настройки объединения.

1. После определения правил дедупликации и настроек объединения нажмите **Далее**.
  
> [!div class="nextstepaction"]
> [Следующий шаг для одной сущности: объединение полей](merge-entities.md)

> [!div class="nextstepaction"]
> [Следующий шаг для нескольких сущностей: условия сопоставления](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Выходные данные дедупликации как сущность

Процесс дедупликации создает новую дедуплицированную сущность для каждой исходной сущности. Эти сущности можно найти вместе с **ConflationMatchPairs:CustomerInsights** в разделе **Система** на странице **Сущности** с именем **Deduplication_DataSource_Entity**.

Сущность выходных данных дедупликации содержит следующую информацию:

- Идентификаторы/ключи
  - Поля первичного ключа и альтернативного идентификатора. Поле альтернативного идентификатора состоит из всех альтернативных идентификаторов, идентифицированных для записи.
  - Поле Deduplication_GroupId показывает группу или кластер, идентифицированный внутри сущности, который группирует все похожие записи на основе указанных полей дедупликации. Это используется для системной обработки. Если не указаны правила ручной дедупликации и применяются системные правила дедупликации, вы можете не найти это поле в сущности выходных данных дедупликации.
  - Deduplication_WinnerId: это поле содержит идентификатор победителя из идентифицированных групп или кластеров. Если Deduplication_WinnerId совпадает со значением первичного ключа для записи, это означает, что запись является победившей.
- Поля, используемые для определения правил дедупликации.
- Поля «Правило» и «Оценка», чтобы указать, какие из правил дедупликации были применены, и оценка, возвращаемая алгоритмом соответствия.

[!INCLUDE[footer-include](includes/footer-banner.md)]