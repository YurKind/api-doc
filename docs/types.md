# Protocol Documentation
<a name="top"/>

## Table of Contents

- [api.proto](#api.proto)
    - [ErrorResult](#ErrorResult)
    - [OnBehalf](#OnBehalf)
    - [Response](#Response)
    - [SuccessResult](#SuccessResult)
  
  
  
  

- [attachments.proto](#attachments.proto)
    - [Attachment](#Attachment)
    - [Attachment.Meta](#Attachment.Meta)
    - [Attachment.Query](#Attachment.Query)
  
  
  
  

- [diagnosis.proto](#diagnosis.proto)
    - [Dz](#Dz)
    - [ShortDz](#ShortDz)
    - [TNM](#TNM)
  
  
  
  

- [directories.proto](#directories.proto)
    - [AddressType](#AddressType)
    - [BloodType](#BloodType)
    - [DiagnosticsType](#DiagnosticsType)
    - [DrDzHD](#DrDzHD)
    - [DrDzMthd](#DrDzMthd)
    - [DrDzPl](#DrDzPl)
    - [DrDzPr](#DrDzPr)
    - [DrDzRA](#DrDzRA)
    - [DrDzSt](#DrDzSt)
    - [DrDzTM](#DrDzTM)
    - [DrDzTS](#DrDzTS)
    - [DrDzWO](#DrDzWO)
    - [DrNK0439](#DrNK0439)
    - [DrNK0465](#DrNK0465)
    - [DrPrsG](#DrPrsG)
    - [DzStage](#DzStage)
    - [FRV442](#FRV442)
    - [KT0365](#KT0365)
    - [LocMet](#LocMet)
    - [LocMetType](#LocMetType)
    - [MedOrg](#MedOrg)
    - [MedOrgType](#MedOrgType)
    - [MedTerr](#MedTerr)
    - [PRK438](#PRK438)
    - [PRP365](#PRP365)
    - [RBiMKB308](#RBiMKB308)
    - [RBiNK0366](#RBiNK0366)
    - [Srv59Oper](#Srv59Oper)
    - [TherapyCond](#TherapyCond)
    - [TnmG](#TnmG)
    - [TnmM](#TnmM)
    - [TnmN](#TnmN)
    - [TnmT](#TnmT)
    - [User](#User)
  
    - [LocMet.Code](#LocMet.Code)
  
  
  

- [meta.proto](#meta.proto)
    - [Object](#Object)
    - [Object.Entry](#Object.Entry)
    - [Query](#Query)
    - [Update](#Update)
    - [Update.Statment](#Update.Statment)
  
    - [Update.Action](#Update.Action)
  
  
  

- [patients.proto](#patients.proto)
    - [Address](#Address)
    - [EHR](#EHR)
    - [Insurance](#Insurance)
    - [Patient](#Patient)
    - [PatientQuery](#PatientQuery)
    - [PatientUpdate](#PatientUpdate)
    - [PatientUpdate.Entry](#PatientUpdate.Entry)
  
  
  
  

- [records.proto](#records.proto)
    - [Rc](#Rc)
    - [Rc.Published](#Rc.Published)
    - [Rc.RcAppointment](#Rc.RcAppointment)
    - [Rc.RcDoc](#Rc.RcDoc)
    - [Rc.RcDz](#Rc.RcDz)
    - [Rc.RcOper](#Rc.RcOper)
    - [Rc.RcReferral](#Rc.RcReferral)
  
  
  
  

- [routing.proto](#routing.proto)
    - [RoutingList](#RoutingList)
    - [RoutingList.Diagnostics](#RoutingList.Diagnostics)
  
  
  
  

- [search.proto](#search.proto)
    - [Page](#Page)
    - [RcAppointmentQuery](#RcAppointmentQuery)
    - [RcDocQuery](#RcDocQuery)
    - [RcReferralQuery](#RcReferralQuery)
    - [RecordsPage](#RecordsPage)
    - [SearchJob](#SearchJob)
  
  
  
  

- [Scalar Value Types](#scalar-value-types)



<a name="api.proto"/>
<p align="right"><a href="#top">Top</a></p>

## api.proto



<a name="ErrorResult"/>

### ErrorResult



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) | required |  |
| message | [string](#string) | optional |  |
| uuid | [string](#string) | optional |  |






<a name="OnBehalf"/>

### OnBehalf



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| first_name | [string](#string) | optional |  |
| middle_name | [string](#string) | optional |  |
| last_name | [string](#string) | optional |  |
| position | [string](#string) | optional |  |






<a name="Response"/>

### Response



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| success | [SuccessResult](#SuccessResult) | optional |  |
| error | [ErrorResult](#ErrorResult) | optional |  |






<a name="SuccessResult"/>

### SuccessResult






 

 

 

 



<a name="attachments.proto"/>
<p align="right"><a href="#top">Top</a></p>

## attachments.proto



<a name="Attachment"/>

### Attachment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [Attachment.Meta](#Attachment.Meta) | required |  |
| data | [bytes](#bytes) | required |  |






<a name="Attachment.Meta"/>

### Attachment.Meta



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| digest | [string](#string) | optional |  |
| name | [string](#string) | required |  |
| type | [string](#string) | required |  |
| size | [int64](#int64) | optional |  |
| created | [string](#string) | optional |  |






<a name="Attachment.Query"/>

### Attachment.Query



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ids | [string](#string) | repeated |  |





 

 

 

 



<a name="diagnosis.proto"/>
<p align="right"><a href="#top">Top</a></p>

## diagnosis.proto



<a name="Dz"/>

### Dz



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| summary | [string](#string) | optional | Примечание |
| icd10 | [RBiMKB308](#RBiMKB308) | optional | МКБ10 |
| status | [DrDzSt](#DrDzSt) | optional | Тип диагноза |
| primacy | [DrDzPr](#DrDzPr) | optional | Первичность установки диагноза |
| morph_class | [RBiNK0366](#RBiNK0366) | optional | Морфологический тип |
| tumor_main | [DrDzTM](#DrDzTM) | optional | Признак основной опухоли |
| tumor_side | [DrDzTS](#DrDzTS) | optional | Сторона поражения |
| how_discover | [DrDzHD](#DrDzHD) | optional | Обстоятельства выявления |
| method | [DrDzMthd](#DrDzMthd) | optional | Метод подтверждения диагноза |
| plural | [DrDzPl](#DrDzPl) | optional | Наличие первично-множественной опухоли |
| resAutopsy | [DrDzRA](#DrDzRA) | optional | Результат аутопсии |
| whyOld | [DrDzWO](#DrDzWO) | optional | Причина поздней диагностики |
| locMet | [LocMet](#LocMet) | optional | Локализация отдаленных метастазов |






<a name="ShortDz"/>

### ShortDz



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| summary | [string](#string) | optional |  |
| mkb_code | [string](#string) | optional |  |
| mkb_name | [string](#string) | optional |  |
| dz_date | [string](#string) | optional |  |
| tnm | [TNM](#TNM) | optional |  |
| dz_stage | [DzStage](#DzStage) | optional |  |
| how_discover | [DrDzHD](#DrDzHD) | optional |  |
| morph_class | [RBiNK0366](#RBiNK0366) | optional |  |
| tumor_main | [DrDzTM](#DrDzTM) | optional |  |
| tumor_side | [DrDzTS](#DrDzTS) | optional |  |
| plural | [DrDzPl](#DrDzPl) | optional |  |






<a name="TNM"/>

### TNM



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| t | [TnmT](#TnmT) | optional |  |
| n | [TnmN](#TnmN) | optional |  |
| m | [TnmM](#TnmM) | optional |  |
| g | [TnmG](#TnmG) | optional |  |





 

 

 

 



<a name="directories.proto"/>
<p align="right"><a href="#top">Top</a></p>

## directories.proto



<a name="AddressType"/>

### AddressType



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="BloodType"/>

### BloodType



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="DiagnosticsType"/>

### DiagnosticsType



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="DrDzHD"/>

### DrDzHD
Запись справочника &#34;Обстоятельства выявления&#34;
   * id = 0 - неизвестно
   * id = 1 - обратился сам
   * id = 2 - активно при профосмотре
   * id = 3 - активно в смотровом кабинете
   * id = 4 - при других обстоятельствах
   * id = 5 - посмертно при аутопсии
   * id = 6 - посмертно без аутопсии


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzMthd"/>

### DrDzMthd
Запись справочника &#34;Метод подтверждения диагноза&#34;
   * id = 0 - неизвестно
   * id = 1 - морфологический
   * id = 2 - цитологический
   * id = 3 - эксплоративная операция
   * id = 4 - лабораторно-инструментальный
   * id = 5 - только клинический


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzPl"/>

### DrDzPl
Запись справочника &#34;Наличие первично-множественной опухоли&#34;
   * id = 0 - неизвестно
   * id = 1 - нет
   * id = 2 - метахронная
   * id = 3 - синхронная
   * id = 4 - синхронно-метахронная


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzPr"/>

### DrDzPr
Запись справочника первичности установки диагноза
   * id = -1 - не установлено
   * id =  0 - неизвестно
   * id =  1 - впервые
   * id =  2 - повторно


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzRA"/>

### DrDzRA
Запись справочника &#34;Результат аутопсии&#34;
   * id = 0 - неизвестно
   * id = 1 - диагноз подтвержден
   * id = 3 - диагноз изменен, другая локализация
   * id = 4 - диагноз изменен, другой морфологический тип
   * id = 5 - диагноз подтвержден &#43; другая локализация
   * id = 6 - рак обнаружен при аутопсии
   * id = 7 - диагноз не подтвержден


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzSt"/>

### DrDzSt
Запись справочника типа диагноза
   * id = 1 - предварительный
   * id = 9 - окончательный


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzTM"/>

### DrDzTM
Запись справочника &#34;Варианты значений основной опухоли диагноза&#34;
   * id = -1 - неизвестно
   * id =  0 - не основная
   * id =  1 - основная


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzTS"/>

### DrDzTS
Запись справочника &#34;Варианты значений стороны опухоли диагноза&#34;
   * id = 1 - слева
   * id = 2 - справа
   * id = 3 - двухсторонняя
   * id = 4 - неприменимо


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrDzWO"/>

### DrDzWO
Запись справочника &#34;Причина поздней диагностики&#34;
   * id = 0 - неизвестно
   * id = 1 - скрытое течение болезни
   * id = 2 - несвоевременное обращение
   * id = 3 - отказ от обследования
   * id = 4 - неполное обследование
   * id = 5 - несовершенство диспансеризации
   * id = 6 - ошибка клиническая
   * id = 7 - ошибка ренгенологическая
   * id = 8 - ошибка морфологическая
   * id = 9 - ошибки других специалистов
   * id = 10 - другие причины


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrNK0439"/>

### DrNK0439
интраоперационное осложнение


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrNK0465"/>

### DrNK0465
справочник операций


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DrPrsG"/>

### DrPrsG
Запись справочника вариантов значений пола человека
   * id = 1 - М
   * id = 2 - Ж
   * id = 3 - не определено


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| id | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="DzStage"/>

### DzStage



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="FRV442"/>

### FRV442



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="KT0365"/>

### KT0365



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="LocMet"/>

### LocMet
Локализация отдаленных метастазов


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| codes | [LocMet.Code](#LocMet.Code) | repeated |  |






<a name="LocMetType"/>

### LocMetType
Запись справочника &#34;Локализация отдаленных метастазов&#34;


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [LocMet.Code](#LocMet.Code) | optional |  |
| caption | [string](#string) | optional |  |






<a name="MedOrg"/>

### MedOrg



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| unq | [string](#string) | optional |  |
| name_full | [string](#string) | optional |  |
| name_short | [string](#string) | optional |  |
| kpp | [string](#string) | optional |  |
| ogrn | [string](#string) | optional |  |
| inn | [string](#string) | optional |  |
| okato | [string](#string) | optional |  |
| post_index | [string](#string) | optional |  |
| address | [string](#string) | optional |  |
| med_terr | [MedTerr](#MedTerr) | optional |  |
| head_med_org_unq | [string](#string) | optional |  |
| org_unit_id | [string](#string) | optional |  |






<a name="MedOrgType"/>

### MedOrgType



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="MedTerr"/>

### MedTerr



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| unq | [string](#string) | optional |  |
| federal_code | [string](#string) | optional |  |
| code | [string](#string) | optional |  |
| name | [string](#string) | optional |  |
| okato | [string](#string) | optional |  |






<a name="PRK438"/>

### PRK438



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="PRP365"/>

### PRP365



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="RBiMKB308"/>

### RBiMKB308
Запись справочника &#34;Международная классификация болезней и состояний,
связанных со здоровьем,  Десятого пересмотра. Версия 2&#34;
(1.2.643.5.1.13.2.1.1.641)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| code | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="RBiNK0366"/>

### RBiNK0366
Запись справочника &#34;Морфологическая классификация новообразований&#34; (1.2.643.5.1.13.2.1.1.495)


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| orid | [string](#string) | optional |  |
| code | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="Srv59Oper"/>

### Srv59Oper
SPONKUSL	Справочник услуг при лечении онкологического заболевания
&lt;p&gt;
Утверждение структур электронных реестров персонифицированного учета медицинской помощи,
передаваемых при информационном взаимодействии между медицинскими организациями и
Территориальным фондом обязательного медицинского страхования Свердловской области в соответствии
с приказом ФФОМС от 30.03.2018 № 59


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |
| group | [int32](#int32) | optional |  |
| index | [int32](#int32) | optional |  |






<a name="TherapyCond"/>

### TherapyCond
условия проведения лечения


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| code | [string](#string) | optional |  |
| caption | [string](#string) | optional |  |






<a name="TnmG"/>

### TnmG



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="TnmM"/>

### TnmM



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="TnmN"/>

### TnmN



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="TnmT"/>

### TnmT



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| caption | [string](#string) | optional |  |






<a name="User"/>

### User



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| login | [string](#string) | optional |  |
| first_name | [string](#string) | optional |  |
| middle_name | [string](#string) | optional |  |
| last_name | [string](#string) | optional |  |
| email | [string](#string) | optional |  |
| description | [string](#string) | optional |  |
| org_unit_id | [string](#string) | optional |  |
| med_terr_id_set | [string](#string) | repeated |  |
| role_name_set | [string](#string) | repeated |  |





 


<a name="LocMet.Code"/>

### LocMet.Code


| Name | Number | Description |
| ---- | ------ | ----------- |
| UNKNOWN | 1 | неизвестно |
| RLN | 2 | отдален. лимф. узлы |
| BONES | 4 | кости |
| LIVER | 8 | печень |
| LUNG | 16 | легкие и/или плевра |
| BRAIN | 32 | головной мозг |
| SKIN | 64 | кожа |
| KIDNEY | 128 | почки |
| OVARY | 256 | яичники |
| PERITONEUM | 512 | брюшина |
| BONE_MARROW | 1024 | костный мозг |
| OTHER_ORGANS | 2048 | другие органы |
| PLURAL | 4096 | множественные |


 

 

 



<a name="meta.proto"/>
<p align="right"><a href="#top">Top</a></p>

## meta.proto



<a name="Object"/>

### Object



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| class_name | [string](#string) | required |  |
| meta | [Object.Entry](#Object.Entry) | repeated |  |






<a name="Object.Entry"/>

### Object.Entry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) | required |  |
| str | [string](#string) | optional |  |
| int32 | [int32](#int32) | optional |  |
| int64 | [int64](#int64) | optional |  |
| float | [float](#float) | optional |  |
| double | [double](#double) | optional |  |
| bool | [bool](#bool) | optional |  |
| date | [string](#string) | optional |  |






<a name="Query"/>

### Query



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ids | [string](#string) | repeated |  |






<a name="Update"/>

### Update



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| statement | [Update.Statment](#Update.Statment) | repeated |  |






<a name="Update.Statment"/>

### Update.Statment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| action | [Update.Action](#Update.Action) | required |  |
| object_id | [string](#string) | required |  |
| meta | [Object.Entry](#Object.Entry) | repeated |  |





 


<a name="Update.Action"/>

### Update.Action


| Name | Number | Description |
| ---- | ------ | ----------- |
| SET | 1 |  |
| REMOVE | 2 |  |


 

 

 



<a name="patients.proto"/>
<p align="right"><a href="#top">Top</a></p>

## patients.proto



<a name="Address"/>

### Address



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| address | [string](#string) | optional |  |
| federal_code | [string](#string) | optional |  |
| region_code | [string](#string) | optional |  |
| town | [string](#string) | optional |  |
| street | [string](#string) | optional |  |
| house | [string](#string) | optional |  |
| flat | [string](#string) | optional |  |
| postal_code | [string](#string) | optional |  |
| fias | [string](#string) | optional |  |
| kladr | [string](#string) | optional |  |
| okato | [string](#string) | optional |  |
| med_terr_unq | [string](#string) | optional |  |
| type | [AddressType](#AddressType) | optional |  |
| living_area_type | [PRK438](#PRK438) | optional |  |






<a name="EHR"/>

### EHR



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| patient_id | [string](#string) | optional |  |
| summary | [string](#string) | optional |  |
| dz | [ShortDz](#ShortDz) | optional |  |






<a name="Insurance"/>

### Insurance



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| insurance_number | [string](#string) | optional |  |






<a name="Patient"/>

### Patient



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| first_name | [string](#string) | optional |  |
| middle_name | [string](#string) | optional |  |
| last_name | [string](#string) | optional |  |
| birth_day | [string](#string) | optional |  |
| gender | [DrPrsG](#DrPrsG) | optional |  |
| code | [string](#string) | optional |  |
| ehr_count | [int32](#int32) | optional |  |
| blood_type | [BloodType](#BloodType) | optional |  |
| social_status | [FRV442](#FRV442) | optional |  |
| company_name | [string](#string) | optional |  |
| company_position | [PRP365](#PRP365) | optional |  |
| snils | [string](#string) | optional |  |
| insurance | [Insurance](#Insurance) | optional |  |
| phones | [string](#string) | optional |  |
| address | [Address](#Address) | optional |  |






<a name="PatientQuery"/>

### PatientQuery



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| first_name | [string](#string) | optional |  |
| middle_name | [string](#string) | optional |  |
| last_name | [string](#string) | optional |  |
| birth_day | [string](#string) | optional |  |
| gender | [DrPrsG](#DrPrsG) | optional |  |
| code | [string](#string) | optional |  |
| snils | [string](#string) | optional |  |
| insurance | [Insurance](#Insurance) | optional |  |






<a name="PatientUpdate"/>

### PatientUpdate



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| code | [string](#string) | required |  |
| entry | [PatientUpdate.Entry](#PatientUpdate.Entry) | repeated |  |






<a name="PatientUpdate.Entry"/>

### PatientUpdate.Entry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| first_name | [string](#string) | optional |  |
| middle_name | [string](#string) | optional |  |
| last_name | [string](#string) | optional |  |
| birth_day | [string](#string) | optional |  |
| gender | [DrPrsG](#DrPrsG) | optional |  |
| blood_type | [BloodType](#BloodType) | optional |  |
| snils | [string](#string) | optional |  |
| insurance | [Insurance](#Insurance) | optional |  |
| phones | [string](#string) | optional |  |





 

 

 

 



<a name="records.proto"/>
<p align="right"><a href="#top">Top</a></p>

## records.proto



<a name="Rc"/>

### Rc



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | optional |  |
| class_name | [string](#string) | optional |  |
| patient_id | [string](#string) | optional |  |
| ehr_id | [string](#string) | optional |  |
| published | [Rc.Published](#Rc.Published) | optional |  |
| org_unit_id | [string](#string) | optional |  |
| summary | [string](#string) | optional |  |
| time_rc | [string](#string) | optional |  |
| attachment_id | [string](#string) | repeated |  |
| rc_doc | [Rc.RcDoc](#Rc.RcDoc) | optional |  |
| rc_referral | [Rc.RcReferral](#Rc.RcReferral) | optional |  |
| rc_appointment | [Rc.RcAppointment](#Rc.RcAppointment) | optional |  |
| rc_dz | [Rc.RcDz](#Rc.RcDz) | optional |  |
| rc_oper | [Rc.RcOper](#Rc.RcOper) | optional |  |






<a name="Rc.Published"/>

### Rc.Published



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| user_id | [string](#string) | optional |  |
| time | [string](#string) | optional |  |






<a name="Rc.RcAppointment"/>

### Rc.RcAppointment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rc_referral_id | [string](#string) | optional |  |
| confirmed | [bool](#bool) | optional |  |
| department | [string](#string) | optional |  |
| doctor | [string](#string) | optional |  |
| consulting_room | [string](#string) | optional |  |
| consulting_date | [string](#string) | optional |  |
| note | [string](#string) | optional |  |






<a name="Rc.RcDoc"/>

### Rc.RcDoc



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| category | [string](#string) | optional |  |
| html | [string](#string) | optional |  |






<a name="Rc.RcDz"/>

### Rc.RcDz



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| diagnosis | [Dz](#Dz) | optional |  |






<a name="Rc.RcOper"/>

### Rc.RcOper



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| operation | [DrNK0465](#DrNK0465) | optional |  |
| condition | [TherapyCond](#TherapyCond) | optional |  |
| org_unit_id | [string](#string) | optional |  |
| intra_compl | [DrNK0439](#DrNK0439) | optional |  |
| after_compl | [DrNK0439](#DrNK0439) | optional |  |
| srv | [Srv59Oper](#Srv59Oper) | repeated |  |






<a name="Rc.RcReferral"/>

### Rc.RcReferral



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rc_appointment_id | [string](#string) | optional |  |
| referral_org_unit_id | [string](#string) | optional |  |
| referral_type | [string](#string) | optional |  |
| purpose | [string](#string) | optional |  |
| routing_list | [RoutingList](#RoutingList) | optional |  |





 

 

 

 



<a name="routing.proto"/>
<p align="right"><a href="#top">Top</a></p>

## routing.proto



<a name="RoutingList"/>

### RoutingList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| apply_last_on_any_other_disease_date | [string](#string) | optional | Date lastVisitOtherSickDate; Дата последнего обращения (госпитализации) по иному заболеванию |
| apply_last_date | [string](#string) | optional | Date lastVisitConsultantLPU; Дата последнего посещения профильной специальности |
| apply_first_date | [string](#string) | optional | Date firstComeLPUDate; Дата первого обращения в ЛПУ по месту жительства по поводу данного заболевания |
| request_date | [string](#string) | optional | Date oodConsultDatePlan; Дата формирования направления с места жительства в ОД // название лучше бы подошло refToODDate |
| admission_date | [string](#string) | optional | Date oodConsultDateFact; Дата фактического приема в ООД |
| examination_lsat_date | [string](#string) | optional | Date oodEndDiagDate; Дата окончания обследования в ОД |
| treatment_first_date | [string](#string) | optional | Date oodStartTherapyDate; дата начала лечения в ОД |
| health_record_code | [string](#string) | optional | String slNumber; номер больничного листа |
| expert_opinion | [string](#string) | optional | String expertConclusion; экспертное заключение |
| expert_opinion_date | [string](#string) | optional | Date expertConclusionDate; дата экспертного заключения |
| note | [string](#string) | optional | String comment; примечание |
| referral_code | [string](#string) | optional | String number; номер направления |
| diagnosis | [ShortDz](#ShortDz) | optional |  |
| diagnostics | [RoutingList.Diagnostics](#RoutingList.Diagnostics) | repeated |  |






<a name="RoutingList.Diagnostics"/>

### RoutingList.Diagnostics



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [DiagnosticsType](#DiagnosticsType) | optional |  |
| date | [string](#string) | optional |  |
| note | [string](#string) | optional |  |





 

 

 

 



<a name="search.proto"/>
<p align="right"><a href="#top">Top</a></p>

## search.proto



<a name="Page"/>

### Page



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| job | [SearchJob](#SearchJob) | required |  |
| offset | [int32](#int32) | optional |  |
| size | [int32](#int32) | optional |  |






<a name="RcAppointmentQuery"/>

### RcAppointmentQuery



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from_date | [string](#string) | optional |  |
| to_date | [string](#string) | optional |  |
| org_unit_id | [string](#string) | optional |  |






<a name="RcDocQuery"/>

### RcDocQuery



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from_date | [string](#string) | optional |  |
| to_date | [string](#string) | optional |  |
| org_unit_id | [string](#string) | optional |  |
| category | [string](#string) | optional |  |






<a name="RcReferralQuery"/>

### RcReferralQuery



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| has_appointment | [bool](#bool) | optional |  |
| from_date | [string](#string) | optional |  |
| to_date | [string](#string) | optional |  |
| from_org_unit_id | [string](#string) | optional |  |
| to_org_unit_id | [string](#string) | optional |  |






<a name="RecordsPage"/>

### RecordsPage



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [Page](#Page) | required |  |
| rc | [Rc](#Rc) | repeated |  |
| size | [int32](#int32) | optional |  |






<a name="SearchJob"/>

### SearchJob



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) | required |  |
| ready | [bool](#bool) | optional |  |
| error | [ErrorResult](#ErrorResult) | optional |  |





 

 

 

 



## Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <a name="double" /> double |  | double | double | float |
| <a name="float" /> float |  | float | float | float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <a name="bool" /> bool |  | bool | boolean | boolean |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |

