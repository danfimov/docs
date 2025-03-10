# Посмотреть историю расходов и скачать отчетные документы в консоли

Физические лица, организации и ИП могут просматривать историю расходов. Организации и ИП, которые являются резидентами Российской Федерации (РФ) и Республики Казахстан (РК), могут скачивать отчетные документы в консоли управления {{ yandex-cloud }}.

{% list tabs %}

- Юридические лица и ИП

  ## Юридическим лицам РФ {#legal-entities-russia}

    Организации и ИП могут скачивать [акты](../concepts/act.md) и [счета-фактуры](../concepts/invoice.md), а также заказывать акты сверки.

    ### Скачать закрывающие документы {#download-closing-docs}

    Акты и счета-фактуры формируются в последний день отчетного периода — месяца. Через 7 рабочих дней после окончания отчетного периода актуальные документы будут доступны для скачивания. Документы за предыдущие отчетные периоды также доступны в консоли управления.

    Чтобы скачать закрывающие документы:
    1. В консоли управления в левом верхнем углу нажмите значок ![image](../../_assets/main-menu.svg) **{{ ui-key.yacloud.iam.folder.dashboard.label_products }}** и выберите сервис [**{{ billing-name }}**]({{ link-console-billing }}).
    1. На странице **{{ ui-key.yacloud.billing.label_accounts }}** выберите платежный аккаунт.
    1. Перейдите в раздел **{{ ui-key.yacloud.billing.account.switch_acts }}**.
    1. Откройте вкладку **{{ ui-key.yacloud.billing.account.tab_acts-title }}**.
    1. В строке с нужным отчетным периодом нажмите ![image](../../_assets/horizontal-ellipsis.svg) → **{{ ui-key.yacloud.billing.account.button_download-action }}**. Откроется окно с отчетными документами за выбранный период.
    1. Справа от документа нажмите ![image](../../_assets/horizontal-ellipsis.svg) → **{{ ui-key.yacloud.common.open }}**. Документ откроется в новой вкладке браузера, и вы сможете его сохранить.

    ### Заказать акт сверки {#download-acts}

    Акты сверки формируются по запросу, который можно оставить в консоли управления {{ yandex-cloud }}. После выполнения запроса документ будет доступен для скачивания.

    Акт сверки за текущий месяц можно заказать спустя 7 рабочих дней после его завершения.

    Чтобы заказать акт сверки:
    1. В консоли управления в левом верхнем углу нажмите значок ![image](../../_assets/main-menu.svg) **{{ ui-key.yacloud.iam.folder.dashboard.label_products }}** и выберите сервис [**{{ billing-name }}**]({{ link-console-billing }}).
    1. На странице **{{ ui-key.yacloud.billing.label_accounts }}** выберите платежный аккаунт.
    1. Перейдите в раздел **{{ ui-key.yacloud.billing.account.switch_acts }}**.
    1. Откройте вкладку **{{ ui-key.yacloud.billing.account.tab_reconciliation-reports-title }}**.
    1. Нажмите на кнопку **{{ ui-key.yacloud.billing.account.reconciliation-reports.action_request-report }}**. В открывшемся окне выберите период, за который требуется сформировать акт сверки, и нажмите **{{ ui-key.yacloud.billing.account.reconciliation-reports.action_request-report-short }}**.
    1. Когда статус запроса изменится на **{{ ui-key.yacloud.billing.account.reconciliation-reports.value_completed }}**, в столбце **{{ ui-key.yacloud.billing.account.reconciliation-reports.field_actions }}** появится кнопка для скачивания. Выберите **{{ ui-key.yacloud.billing.account.reconciliation-reports.action_download-with-facsimile }}** или **{{ ui-key.yacloud.billing.account.reconciliation-reports.action_download-without-facsimile }}**.

       {% cut "Обмен оригиналами документов" %}

       Для обмена оригиналами документов, пожалуйста, скачайте акт без подписи, распечатайте 2 экземпляра, подпишите их и отправьте:

       * Почтой России: 115035, г. Москва, ул. Садовническая, д. 82, стр. 2.
          На конверте укажите <q>для группы по сопровождению проектных сделок</q> и, пожалуйста, не используйте имена сотрудников.
   
       * Курьером: 115035, г. Москва, ул. Садовническая, д. 82, стр. 2.
          Вход с Садовнической улицы, между 5 и 6 подъездами БЦ <q>Аврора</q>.
          Курьерский ресепшен работает с понедельника по пятницу с 9:00 до 18:00.
          Телефон канцелярии: +7(495)739-70-00, далее нажмите 1, а после включения голосового меню — 7704.

       Документы будут подписаны, и вам отправят ваш экземпляр.

       {% endcut %}

    1. Нажмите кнопку с выбранным типом скачивания. Документ откроется в новом окне, и вы сможете его сохранить.

  ## Юридическим лицам РК {#legal-entities-kazakhstan}

    ### Акт выполненных работ {#report-of-completion}

    Организации и ИП, которые являются резидентами РK, могут скачивать акты выполненных работ (АВР).

    Документы формируются в последний день отчетного периода — месяца. Через 7 рабочих дней после окончания отчетного периода акт выполненных работ будет доступен для скачивания. АВР за предыдущие отчетные периоды также доступны в консоли управления.

    Чтобы заказать акт выполненных работ:
    1. В консоли управления в левом верхнем углу нажмите значок ![image](../../_assets/main-menu.svg) **{{ ui-key.yacloud.iam.folder.dashboard.label_products }}** и выберите сервис [**{{ billing-name }}**]({{ link-console-billing }}).
    1. На странице **{{ ui-key.yacloud.billing.label_accounts }}** выберите платежный аккаунт.
    1. Перейдите в раздел **{{ ui-key.yacloud.billing.account.switch_acts }}**.
    1. Откройте вкладку **{{ ui-key.yacloud.billing.account.tab_acts-title }}**.
    1. В строке с нужным отчетным периодом нажмите ![image](../../_assets/horizontal-ellipsis.svg) → **{{ ui-key.yacloud.billing.account.button_download-action }}**. Откроется окно с актами за выбранный период.
    1. Справа от документа нажмите ![image](../../_assets/horizontal-ellipsis.svg) → **{{ ui-key.yacloud.common.open }}**. Документ откроется в новой вкладке браузера, и вы сможете его сохранить.

    ### Электронный счет-фактура {#electronic-invoice}

    Электронные счета-фактуры (ЭСФ) отправляются в [Информационную систему по приему и обработке электронных счетов-фактур](https://esf.gov.kz:8443/esf-web/login) (ИС ЭСФ) не позднее, чем через 15 календарных дней после даты совершения оборота по реализации.

- Физические лица

  ## Посмотреть историю расходов {#expense-history}

  Физические лица, которые являются резидентами РФ, могут просматривать историю расходов помесячно в консоли управления {{ yandex-cloud }}.

  Чтобы посмотреть историю расходов:
    1. В консоли управления в левом верхнем углу нажмите значок ![image](../../_assets/main-menu.svg) **{{ ui-key.yacloud.iam.folder.dashboard.label_products }}** и выберите сервис [**{{ billing-name }}**]({{ link-console-billing }}).
    1. На странице **{{ ui-key.yacloud.billing.label_accounts }}** выберите платежный аккаунт.
    1. Перейдите в раздел **{{ ui-key.yacloud.billing.account.switch_expences }}**.

  Для физических лиц недоступно скачивание отчетных документов.

{% endlist %}