# Zp365

[Авторизация][#авторизация]
[Обновить токены][#обновить-токены]
[Активация пользователя][#активация-пользователя]
[Статус активации пользователей][#статус-активации-пользователей]
[Выплата][#выплата]
[Статус выплаты][#статус-выплаты]
[Cотрудники][#сотрудники]
[Сущности][#сущности]


## Авторизация

### Запрос
- POST /auth/token

### Headers
- Content-Type: application/json

### Body

```json
{
    "phone":"79999999999",
    "password": "eyJhbGciOiJI"
}
```

### Ответ

```json
{
    "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW50aXR5IjoiT3JnYW5pemF0aW9uRW50aXR5IiwiaWF0IjoxNjY5MDIwNjkyLCJleHAiOjE2NjkwMjA5OTJ9._fPHkDsvnPeArNqBMru6YP_4pAtlpZfhb7-p6YQgDw0",
    "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW50aXR5IjoiT3JnYW5pemF0aW9uRW50aXR5IiwiaWF0IjoxNjY5MDIwNjkyLCJleHAiOjE2NjkxMDcwOTJ9.BFjT3pXs2c3J747vWCNX2UTmt7LwRRhzoUi-q1sTA9o"
}
```



## Обновить токены

### Запрос
- GET /auth/token/refresh

### Headers
- Authorization: Bearer `refresh`

### Ответ

```json
{
    "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW50aXR5IjoiT3JnYW5pemF0aW9uRW50aXR5IiwiaWF0IjoxNjY5MDIwNjkyLCJleHAiOjE2NjkwMjA5OTJ9._fPHkDsvnPeArNqBMru6YP_4pAtlpZfhb7-p6YQgDw0",
    "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MiwiZW50aXR5IjoiT3JnYW5pemF0aW9uRW50aXR5IiwiaWF0IjoxNjY5MDIwNjkyLCJleHAiOjE2NjkxMDcwOTJ9.BFjT3pXs2c3J747vWCNX2UTmt7LwRRhzoUi-q1sTA9o"
}
```


## Активация пользователя

### Запрос
- POST /integration/activate

### Headers
- Authorization: Bearer `access`

### Body 
array of objects

```json
[
      {
         "organization":"1234567890",
         "individual":{
            "organization":"1234567890",
            "individual_external_id":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
            "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f00",
            "phone":"77217676667",
            "email":"sibusiso.garza@yahoo.net",
            "fname":"string",
            "iname":"string",
            "oname":"string",
            "gender":1,
            "inn":"string",
            "snils":"31695936819",
            "birth_date":"2022-06-21T07:06:38.286Z",
            "birth_place":"string",
            "citizenship":"string",
            "doc_kind":"string",
            "doc_series":"string",
            "doc_number":"string",
            "doc_issued_by":"string",
            "doc_issued_date":"2022-06-21T07:06:38.286Z",
            "doc_department_code":"string",
            "doc_expired_at":"2022-06-21T07:06:38.286Z",
            "reg_address":"string",
            "fact_address":"string",
            "education_kind":"string",
            "posthigh_education_kind":"string",
            "institution":"string",
            "speciality":"string",
            "qualification":"string",
            "regional_premium_rate":1000,
            "northern_hardship_bonus":[
               "test"
            ]
         },
         "employee":[
            {
               "organization":"string",
               "individual_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "employee_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "employee_guid":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "tab_num":"string",
               "department":"string",
               "position":"string",
               "is_combined":false,
               "count":1.00,
               "admission_date":"2022-06-21T07:06:38.286Z",
               "probation_end_date":"2022-06-21T07:06:38.286Z",
               "salary":180000,
               "planned_deduction":1000.50,
               "deduction_rate":1000.123123123123,
               "termination_date":"2022-06-21T07:06:38.286Z",
               "tax_rate":123123123
            },
            {
               "organization":"string",
               "individual_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "employee_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "employee_guid":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "tab_num":"string",
               "department":"string",
               "position":"string",
               "is_combined":false,
               "count":1.00000000000000000000,
               "admission_date":"2022-06-21T07:06:38.286Z",
               "probation_end_date":"2022-06-21T07:06:38.286Z",
               "salary":120000,
               "planned_deduction":1000,
               "deduction_rate":1000,
               "termination_date":"2022-06-21T07:06:38.286Z",
               "tax_rate":1000
            }
         ],
         "bank_props":[
            {
               "organization":"string",
               "individual_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "is_active":true,
               "bik":"43304728",
               "inn":"string",
               "kpp":"string",
               "bank_name":"ПАО СБЕРБАНК-Центр",
               "correspondent_account":"string",
               "checking_account":"string",
               "fio":"string"
            },
            {
               "organization":"string",
               "individual_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "is_active":false,
               "bik":"string",
               "inn":"string",
               "kpp":"string",
               "bank_name":"string",
               "correspondent_account":"string",
               "checking_account":"string",
               "fio":"string"
            }
         ],
         "payment_sheets":[
            {
               "organization":"string",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "period":"2022-06-21T09:31:31.522Z",
               "contribution_pfr":0.00,
               "contribution_fss":0.00,
               "contribution_accident_fss":0.00,
               "contribution_ffoms":0.00,
               "average_salary":0.00,
               "payments":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "days":0.00,
                     "hours":0.00,
                     "result":0.00
                  }
               ],
               "deductions":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "result":0.00
                  }
               ],
               "accrueds":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "result":0.00
                  }
               ]
            },
            {
               "organization":"string",
               "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
               "period":"2022-06-21T09:31:31.522Z",
               "contribution_pfr":0.00,
               "contribution_fss":0.00,
               "contribution_accident_fss":0.00,
               "contribution_ffoms":0.00,
               "average_salary":0.00,
               "payments":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "days":0.00,
                     "hours":0.00,
                     "result":0.00
                  }
               ],
               "deductions":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "result":0.00
                  }
               ],
               "accrueds":[
                  {
                     "guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                     "name":"string",
                     "period":"2022-06-21T09:31:31.522Z",
                     "result":0.00
                  }
               ]
            }
         ],
         "settlements": [
             {
                "organization": "string",
                "individual_external_id": "0ce8882f-5f5c-44ac-bd27-e761cdb86ba3",
                "individual_guid": "89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
                "document_external_id": "0ce8882f-5f5c-44ac-bd27-e761cdb86ba3",
                "document_guid": "string",
                "name": "string",
                "period": "2022-07-04T08:55:36.665Z",
                "payment_method": "string",
                "rev": 1111,
                "remainder": 0.00,
                "income_code": "strin",
                "payment_order_code": "string",
                "payment_order_date": "2022-07-04T08:55:36.665Z"
                }
         ],
         "vacation_remainder": {
            "organization": "string",
            "employee_guid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "count": 0
        },
         "work_schedule": {
            "organization": "string",
            "employee_external_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "employee_guid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "year": 9999,
            "month": 12,
            "days": [
                {
                    "date": "2022-09-04T15:18:34.351Z",
                    "hours": 2,
                    "is_holiday": false
                }
            ]
        }
      }
]
```

### Ответ

```json
{
    "status": "ok",
    "keys": [
        {
            "id": "540",
            "individual_guid": "89fb2a77-b27b-4767-a51b-9b1d6c6c6f00"
        }
    ]
}
```


## Статус активации пользователей

### Запрос
- POST /integration/activate/status

### Headers
- Authorization: Bearer `access`

### Body

```json
{
  "keys": [
    "528"
  ]
}
```

### Ответ

```typescript
{//промежуточный
    id: string | number;
    data: any;
    timestamp: number;
    message?: string;
}
{// успешный окончательный
    id: string | number;
    data: any;
    timestamp: number;
    finishedOn: number | null;
    message?: string;
}
{// ошибочный окончательный
    id: string | number;
    data: any;
    timestamp: number;
    finishedOn: number | null;
    failedReason: string;
    message?: string;
}
```

## Выплата

### Запрос
- POST /integration/update/settlements

### Headers
- Authorization: Bearer `access`

### Body
array of objects as settlement
```json
[
  {
    "organization": "9953435907",
    "individual_external_id": "9da58e3b-946c-4bdc-bfc5-e4f1df3e0340",
    "individual_guid": "b7f843fd-436e-4e88-880a-c8157e4d0826",
    "document_external_id": "12f37b6c-c25d-45e3-9df4-767996622be1",
    "document_guid": "9c12ecda-a26a-4bc6-b51d-50ac4f436357",
    "name": "Сохраняем данные о выплате",
    "period": "2022-08-16T07:17:00.352Z",
    "payment_method": "string",
    "rev": 1000,
    "remainder": 100.00,
    "income_code": "strin",
    "payment_order_code": "string",
    "payment_order_date": "2022-07-05T07:17:00.352Z"
  }
]
```

### Ответ

```json
{
  "status": "ok",
  "keys": [
    {
      "id": "119",
      "individual_guid": "b7f843fd-436e-4e88-880a-c8157e4d0826"
    }
  ]
}
```


## Статус выплаты

### Запрос
- POST /integration/update/settlements/status

### Headers
- Authorization: Bearer `access`

### Body

```json
{
  "keys": [
    "528"
  ]
}
```

### Ответ

```typescript
{//промежуточный
    id: string | number;
    data: any;
    timestamp: number;
    message?: string;
}
{// успешный окончательный
    id: string | number;
    data: any;
    timestamp: number;
    finishedOn: number | null;
    message?: string;
}
{// ошибочный окончательный
    id: string | number;
    data: any;
    timestamp: number;
    finishedOn: number | null;
    failedReason: string;
    message?: string;
}
```


## Cотрудники

### Запрос
- GET /employee-list?page=1

### Headers
- Authorization: Bearer `access`

### QUERY PARAM
```text
?page=1
```

### Ответ

```json
{
  "bank_props": [
    {
      "organization":"string",
      "individual_external_id":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "individual_guid":"89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
      "is_active":true,
      "bik":"43304728",
      "inn":"string",
      "kpp":"string",
      "bank_name":"ПАО СБЕРБАНК-Центр",
      "correspondent_account":"string",
      "checking_account":"string",
      "fio":"string"
    }
  ],
  "settlements": [
    {
        "organization": "string",
        "individual_external_id": "0ce8882f-5f5c-44ac-bd27-e761cdb86ba3",
        "individual_guid": "89fb2a77-b27b-4767-a51b-9b1d6c6c6f44",
        "document_external_id": "0ce8882f-5f5c-44ac-bd27-e761cdb86ba3",
        "document_guid": "string",
        "name": "string",
        "period": "2022-07-04T08:55:36.665Z",
        "payment_method": "string",
        "rev": 1111,
        "remainder": 0.00,
        "income_code": "strin",
        "payment_order_code": "string",
        "payment_order_date": "2022-07-04T08:55:36.665Z"
      }
  ]
}
```


## Сущности

**Данные физ.лица**
```yaml
individual:
    title: Данные физ.лица
    required:
      - organization
      - fname
      - iname
      - gender
      - snils
      - birth_date
      - doc_series
      - doc_number
      - doc_issued_date
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      individual_external_id:
        title: Внешний идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      individual_guid:
        title: Идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      phone:
        title: Телефон
        type: string
        maxLength: 128
      email:
        title: Email
        type: string
        format: email
      fname:
        title: Фамилия
        type: string
        minLength: 1
      iname:
        title: Имя
        type: string
        minLength: 1
      oname:
        title: Отчество
        type: string
      gender:
        title: Пол
        description: 'Допустимые значения: 1 (Мужской), 2 (Женский)'
        type: string
      inn:
        title: ИНН
        type: string
        maxLength: 12
      snils:
        title: СНИЛС
        type: string
        maxLength: 14
        minLength: 1
      birth_date:
        title: Дата рождения
        type: string
        format: date-time
      birth_place:
        title: Место рождения
        type: string
        maxLength: 240
      citizenship:
        title: Гражданство
        type: string
        maxLength: 60
      doc_kind:
        title: Вид документа
        type: string
        maxLength: 150
      doc_series:
        title: Серия документа
        type: string
        maxLength: 14
        minLength: 1
      doc_number:
        title: Номер документа
        type: string
        maxLength: 14
        minLength: 1
      doc_issued_by:
        title: Место выдачи документа
        type: string
        maxLength: 200
      doc_issued_date:
        title: Дата выдачи документа
        type: string
        format: date-time
      doc_department_code:
        title: Код подразделения
        type: string
        maxLength: 150
      doc_expired_at:
        title: Срок окончания действия документа
        type: string
        format: date-time
        x-nullable: true
      reg_address:
        title: Адрес регистрации
        type: string
        maxLength: 500
      fact_address:
        title: Адрес фактического проживания
        type: string
        maxLength: 500
      education_kind:
        title: Вид образования
        type: string
        maxLength: 70
      posthigh_education_kind:
        title: Вид послевузовского образования
        type: string
        maxLength: 70
      institution:
        title: Учебное заведение
        type: string
        maxLength: 150
      speciality:
        title: Специальность
        type: string
        maxLength: 100
      qualification:
        title: Квалификация
        type: string
        maxLength: 100
      regional_premium_rate:
        title: Районный коэффициент
        type: string
        format: decimal
        x-nullable: true
      northern_hardship_bonus:
        type: array of string
        default: []
```

**Кадровые данные**
```yaml
employee:
    title: Кадровые данные
    required:
      - organization
      - admission_date
      - salary
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      individual_external_id:
        title: Внешний идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      individual_guid:
        title: Идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      employee_external_id:
        title: Внешний идентификатор сотрудника
        type: string
        minLength: 1
        x-nullable: true
      employee_guid:
        title: Идентификатор сотрудника
        type: string
        format: uuid
        x-nullable: true
      tab_num:
        title: Табельный номер
        type: string
        maxLength: 64
      department:
        title: Подразделение
        type: string
        maxLength: 150
      position:
        title: Должность
        type: string
        maxLength: 150
      is_combined:
        title: Признак совместительства
        type: boolean
        default: false
      count:
        title: Количество ставок
        type: string
        format: decimal
        default: '1.00000000000000000000'
      admission_date:
        title: Дата приема на работу
        type: string
        format: date-time
      probation_end_date:
        title: Дата окончания испытательного периода
        type: string
        format: date-time
        x-nullable: true
      salary:
        title: Оклад
        type: string
        format: decimal
      planned_deduction:
        title: Сумма планируемых удержаний
        type: string
        format: decimal
        x-nullable: true
      deduction_rate:
        title: Процент удержаний
        type: string
        format: decimal
        x-nullable: true
      termination_date:
        title: Дата увольнения
        type: string
        format: date-time
        x-nullable: true
      tax_rate:
        title: Налоговая ставка
        type: string
        format: decimal
        x-nullable: true
```

**Банковские реквизиты**
```yaml
bank_props:
    title: Банковские реквизиты
    required:
      - organization
      - bik
      - bank_name
      - checking_account
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      individual_external_id:
        title: Внешний идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      individual_guid:
        title: Идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: true
      is_active:
        title: Признак актуальности
        type: boolean
        default: true
      bik:
        title: БИК
        type: string
        maxLength: 9
        minLength: 1
      inn:
        title: ИНН
        type: string
        maxLength: 12
      kpp:
        title: КПП
        type: string
        maxLength: 9
      bank_name:
        title: Наименование банка
        type: string
        maxLength: 100
        minLength: 1
      correspondent_account:
        title: Корреспондентский счет
        type: string
        maxLength: 20
      checking_account:
        title: Расчетный счет
        type: string
        maxLength: 20
        minLength: 1
      fio:
        title: ФИО получателя
        type: string
        maxLength: 512
        x-nullable: true
```

**Список расчетных листов сотрудника за последние 12 месяцев**
```yaml
  payment_sheets:
    required:
      - contribution_pfr
      - contribution_fss
      - contribution_accident_fss
      - contribution_ffoms
      - fname
      - iname
      - oname
    type: object
    properties:
      accruals:
        type: array
        items:
          $ref: '#/definitions/Accrual'
        readOnly: true
      deductions:
        type: array
        items:
          $ref: '#/definitions/Deduction'
        readOnly: true
      payments:
        type: array
        items:
          $ref: '#/definitions/Payment'
        readOnly: true
      contribution_pfr:
        title: Сумма взносов в ПФР
        type: string
        format: decimal
      contribution_fss:
        title: Сумма взносов в ФСС
        type: string
        format: decimal
      contribution_accident_fss:
        title: Сумма взносов в ФСС (травматизм)
        type: string
        format: decimal
      contribution_ffoms:
        title: Сумма взносов в ФФОМС
        type: string
        format: decimal
      date:
        title: Дата
        type: string
        readOnly: true
      fname:
        title: Fname
        type: string
        minLength: 1
      iname:
        title: Iname
        type: string
        minLength: 1
      oname:
        title: Oname
        type: string
      salary:
        title: Оклад
        type: string
        readOnly: true
      position:
        title: Должность
        type: string
        readOnly: true
      accruals_amount:
        title: Общая сумма выплат
        type: string
        readOnly: true
      deductions_amount:
        title: Общая сумма удержаний
        type: string
        readOnly: true
      payments_amount:
        title: Общая сумма начислений
        type: string
        readOnly: true
      withdraws_amount:
        title: Общая сумма ранних выводов
        type: string
        readOnly: true
      commissions_amount:
        title: Общая сумма комиссий
        type: string
        readOnly: true
```


**Взаиморасчеты сотрудника**
Если rev отрицательный - это выплата, иначе просто сохраняем эти данные без произведения выплаты.
```yaml
  settlements:
    title: Взаиморасчеты сотрудника
    required:
      - organization
      - name
      - period
      - rev
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      individual_external_id:
        title: Внешний идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: false
      individual_guid:
        title: Идентификатор физ.лица
        type: string
        minLength: 1
        x-nullable: false
      document_external_id:
        title: Внешний идентификатор документа
        type: string
        minLength: 1
        x-nullable: false
      document_guid:
        title: Идентификатор документа, изменившего состояние взаиморасчетов с физ.лицом
        type: string
        maxLength: 255
        minLength: 1
        x-nullable: false
      name:
        title: Представление регистратора
        type: string
        maxLength: 100
        minLength: 1
      period:
        title: Дата получения остатков взаиморасчетов
        type: string
        format: date-time
      payment_method:
        title: Вид выплаты из ведомости
        type: string
      rev:
        title: Оборот
        type: string
        format: decimal
      remainder:
        title: Остаток задолженности перед сотрудником
        type: string
        format: decimal
        default: '0.00'
      Income_code:
        title: Код дохода
        type: string
        maxLength: 5
        x-nullable: true
      payment_order_code:
        title: Номер платежа
        type: string
        maxLength: 10
      payment_order_date:
        title: Дата платежа
        type: string
        format: date-time
        x-nullable: true
```


**Остатки отпусков**
```yaml
  vacation_remainder:
    title: Остатки отпусков
    required:
      - organization
      - employee_guid
      - count
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      employee_guid:
        title: Идентификатор сотрудника
        type: string
        format: uuid
      count:
        title: Остаток дней отпуска
        type: integer
```

**График работы**
```yaml
work_schedule:
    title: График работы
    required:
      - organization
      - year
      - month
      - days
    type: object
    properties:
      organization:
        title: ИНН/КПП организации
        type: string
        maxLength: 22
        minLength: 1
      employee_external_id:
        title: Внешний идентификатор сотрудника
        type: string
        minLength: 1
        x-nullable: true
      employee_guid:
        title: Идентификатор сотрудника
        type: string
        format: uuid
        x-nullable: true
      year:
        title: Год
        type: integer
        maximum: 9999
      month:
        title: Месяц
        type: integer
        maximum: 12
      days:
        type: array
        items:
          $ref: work_schedule_day // Список дней
```

**Список дней**
```yaml
  work_schedule_day:
    title: Список дней
    required:
      - date
      - hours
    type: object
    properties:
      date:
        title: День
        type: string
        format: date-time
      hours:
        title: Количество запланированных часов
        type: string
        format: decimal
      is_holiday:
        title: Признак выходного (нерабочего) дня
        type: boolean
        default: false
```
