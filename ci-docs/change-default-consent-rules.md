---
title: Управление правилами согласия по умолчанию для сегментов
description: С помощью функции управления согласием вы можете отключить или изменить правила согласия по умолчанию, если включены переопределения.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755232"
---
# <a name="disable-or-change-default-consent-rules"></a>Отключение или изменение правил согласия по умолчанию

Если ваша организация использует [возможность управления согласием](consent-management/overview.md) в сочетании с Dynamics 365 Customer Insights, [администраторы могут принудительно включить правила согласия](activate-consent.md) для сегментов. 

При применении принудительных правил согласия в области сегментов каждый сегмент информирует о состоянии проверки и правил согласия. Если переопределения разрешены, правила согласия по умолчанию для определенных сегментов отключены. Каждый создатель сегмента может добавить дополнительные правила поверх предусмотренных по умолчанию для данного сегмента. 

## <a name="for-administrators"></a>Для администраторов

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Конструктор сегментов с параметрами правила согласия.":::

**Чтобы отключить правила согласия по умолчанию:**

1. В уведомлении **Правила согласия** выберите **Показать подробности**. 

1. Установите переключатель **Правила согласия по умолчанию** в положение **Откл.**.

**Чтобы добавить дополнительные правила согласия:**

1. В уведомлении **Правила согласия** выберите **Показать подробности**. 

1. Выберите **Добавить правила согласия** и выберите правило согласия из раскрывающегося списка **Выберите тип данных согласия**.

1. Выберите **Сохранить**, чтобы применить новое правило к сегменту.

## <a name="for-contributors"></a>Для участников

Чтобы создать сегмент без принудительных правил согласия, вам нужно обратиться к своему администратору и попросить его отключить их в вашем сегменте. Тем не менее вы можете добавлять свои собственные правила согласия к сегментам, которыми вы владеете и управляете.

Этот процесс включает в себя три этапа: 
1. [Создайте сегмент](segments.md) в Customer Insights и сохраните его. 

1. Сообщите имя сегмента своему администратору и попросите его [включить переопределения для вашего сегмента](activate-consent.md). 

1. Снова откройте свои сегменты. В уведомлении **Правила согласия** выберите **Показать подробности** и добавьте правила согласия, которые вы хотите применить. Затем **Сохраните** и **Запустите** сегмент.



[!INCLUDE [footer-include](includes/footer-banner.md)] 