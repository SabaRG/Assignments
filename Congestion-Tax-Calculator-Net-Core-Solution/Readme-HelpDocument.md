<a name='assembly'></a>
# Congestion-Tax-Calculator-Net-Core

## Contents

- [CSVTaxRuleRepository](#T-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository 'congestion.calculator.v2.Infrastructure.Providers.CSVTaxRuleRepository')
  - [#ctor(filePath)](#M-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository-#ctor-System-String- 'congestion.calculator.v2.Infrastructure.Providers.CSVTaxRuleRepository.#ctor(System.String)')
  - [GetAllRules(city)](#M-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository-GetAllRules-System-String- 'congestion.calculator.v2.Infrastructure.Providers.CSVTaxRuleRepository.GetAllRules(System.String)')
- [CongestionTaxCalculator](#T-congestion-calculator-CongestionTaxCalculator 'congestion.calculator.CongestionTaxCalculator')
  - [GetTax()](#M-congestion-calculator-CongestionTaxCalculator-GetTax-congestion-calculator-IVehicle,System-DateTime[]- 'congestion.calculator.CongestionTaxCalculator.GetTax(congestion.calculator.IVehicle,System.DateTime[])')
- [CongestionTaxCalculatorV1](#T-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV1 'congestion.calculator.v2.Application.Services.CongestionTaxCalculatorV1')
  - [GetTax(vehicle,dates)](#M-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV1-GetTax-congestion-calculator-IVehicle,System-DateTime[]- 'congestion.calculator.v2.Application.Services.CongestionTaxCalculatorV1.GetTax(congestion.calculator.IVehicle,System.DateTime[])')
- [CongestionTaxCalculatorV2](#T-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV2 'congestion.calculator.v2.Application.Services.CongestionTaxCalculatorV2')
  - [GetTax(vehicle,dates)](#M-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV2-GetTax-congestion-calculator-IVehicle,System-DateTime[]- 'congestion.calculator.v2.Application.Services.CongestionTaxCalculatorV2.GetTax(congestion.calculator.IVehicle,System.DateTime[])')
- [DateTollFeeStrategyV1](#T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV1')
  - [GetDateTollFee(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1-GetDateTollFee-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV1.GetDateTollFee(System.DateTime)')
  - [IsTollFreeDate(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1-IsTollFreeDate-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV1.IsTollFreeDate(System.DateTime)')
- [DateTollFeeStrategyV2](#T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV2')
  - [GetDateTollFee(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2-GetDateTollFee-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV2.GetDateTollFee(System.DateTime)')
  - [IsTollFreeDate(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2-IsTollFreeDate-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV2.IsTollFreeDate(System.DateTime)')
- [DateTollFeeStrategyV3](#T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV3')
  - [#ctor(taxRuleRepository,city)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-#ctor-congestion-calculator-v2-Infrastructure-Repositories-ITaxRuleRepository,System-String- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV3.#ctor(congestion.calculator.v2.Infrastructure.Repositories.ITaxRuleRepository,System.String)')
  - [GetDateTollFee(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-GetDateTollFee-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV3.GetDateTollFee(System.DateTime)')
  - [IsTollFreeDate(date)](#M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-IsTollFreeDate-System-DateTime- 'congestion.calculator.v2.Application.Services.DateTollFeeStrategyV3.IsTollFreeDate(System.DateTime)')
- [Extensions](#T-congestion-calculator-v2-Domain-ValueObjects-Extensions 'congestion.calculator.v2.Domain.ValueObjects.Extensions')
- [ICongestionTaxCalculatorStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-ICongestionTaxCalculatorStrategy 'congestion.calculator.v2.Application.Services.Interfaces.ICongestionTaxCalculatorStrategy')
  - [GetTax(vehicle,dates)](#M-congestion-calculator-v2-Application-Services-Interfaces-ICongestionTaxCalculatorStrategy-GetTax-congestion-calculator-IVehicle,System-DateTime[]- 'congestion.calculator.v2.Application.Services.Interfaces.ICongestionTaxCalculatorStrategy.GetTax(congestion.calculator.IVehicle,System.DateTime[])')
- [IDateTollFeeStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy 'congestion.calculator.v2.Application.Services.Interfaces.IDateTollFeeStrategy')
  - [GetDateTollFee(date)](#M-congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy-GetDateTollFee-System-DateTime- 'congestion.calculator.v2.Application.Services.Interfaces.IDateTollFeeStrategy.GetDateTollFee(System.DateTime)')
- [ITollFeeCalculatorStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-ITollFeeCalculatorStrategy 'congestion.calculator.v2.Application.Services.Interfaces.ITollFeeCalculatorStrategy')
  - [GetTollFee(vehicle,date)](#M-congestion-calculator-v2-Application-Services-Interfaces-ITollFeeCalculatorStrategy-GetTollFee-congestion-calculator-IVehicle,System-DateTime- 'congestion.calculator.v2.Application.Services.Interfaces.ITollFeeCalculatorStrategy.GetTollFee(congestion.calculator.IVehicle,System.DateTime)')
- [IVehicleTollFeeStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy 'congestion.calculator.v2.Application.Services.Interfaces.IVehicleTollFeeStrategy')
  - [IsVehicleTollFree(vehicle)](#M-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy-IsVehicleTollFree-congestion-calculator-IVehicle- 'congestion.calculator.v2.Application.Services.Interfaces.IVehicleTollFeeStrategy.IsVehicleTollFree(congestion.calculator.IVehicle)')
- [IVehicleV2](#T-congestion-calculator-v2-Application-Services-Interfaces-IVehicleV2 'congestion.calculator.v2.Application.Services.Interfaces.IVehicleV2')
- [MDTaxRuleRepository](#T-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository 'congestion.calculator.v2.Infrastructure.Providers.MDTaxRuleRepository')
  - [#ctor(filePath)](#M-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository-#ctor-System-String- 'congestion.calculator.v2.Infrastructure.Providers.MDTaxRuleRepository.#ctor(System.String)')
  - [GetAllRules(city)](#M-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository-GetAllRules-System-String- 'congestion.calculator.v2.Infrastructure.Providers.MDTaxRuleRepository.GetAllRules(System.String)')
- [MainCongestionTaxCalculatorNew](#T-congestion-calculator-v2-Application-Services-MainCongestionTaxCalculatorNew 'congestion.calculator.v2.Application.Services.MainCongestionTaxCalculatorNew')
- [Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time')
  - [#ctor(ticks)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-Int64- 'congestion.calculator.v2.Domain.ValueObjects.Time.#ctor(System.Int64)')
  - [#ctor(hour,minute,second,millisecond)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-Int32,System-Int32,System-Int32,System-Int32- 'congestion.calculator.v2.Domain.ValueObjects.Time.#ctor(System.Int32,System.Int32,System.Int32,System.Int32)')
  - [#ctor(dt)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.#ctor(System.DateTime)')
  - [#ctor(timeString)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-String- 'congestion.calculator.v2.Domain.ValueObjects.Time.#ctor(System.String)')
  - [AsDateTime](#P-congestion-calculator-v2-Domain-ValueObjects-Time-AsDateTime 'congestion.calculator.v2.Domain.ValueObjects.Time.AsDateTime')
  - [CompareTo(other)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-CompareTo-congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.CompareTo(congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [CompareTo(other)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-CompareTo-System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.CompareTo(System.DateTime)')
  - [Equals(obj)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-Equals-System-Object- 'congestion.calculator.v2.Domain.ValueObjects.Time.Equals(System.Object)')
  - [GetHashCode()](#M-congestion-calculator-v2-Domain-ValueObjects-Time-GetHashCode 'congestion.calculator.v2.Domain.ValueObjects.Time.GetHashCode')
  - [ToString()](#M-congestion-calculator-v2-Domain-ValueObjects-Time-ToString 'congestion.calculator.v2.Domain.ValueObjects.Time.ToString')
  - [op_Equality(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Equality-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_Equality(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_Equality(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Equality-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_Equality(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
  - [op_GreaterThan(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThan-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_GreaterThan(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_GreaterThan(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThan-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_GreaterThan(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
  - [op_GreaterThanOrEqual(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_GreaterThanOrEqual(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_GreaterThanOrEqual(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_GreaterThanOrEqual(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
  - [op_Inequality(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Inequality-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_Inequality(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_Inequality(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Inequality-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_Inequality(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
  - [op_LessThan(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThan-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_LessThan(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_LessThan(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThan-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_LessThan(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
  - [op_LessThanOrEqual(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_LessThanOrEqual(congestion.calculator.v2.Domain.ValueObjects.Time,congestion.calculator.v2.Domain.ValueObjects.Time)')
  - [op_LessThanOrEqual(left,right)](#M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime- 'congestion.calculator.v2.Domain.ValueObjects.Time.op_LessThanOrEqual(congestion.calculator.v2.Domain.ValueObjects.Time,System.DateTime)')
- [TollFeeStrategyV1](#T-congestion-calculator-v2-Application-Services-TollFeeStrategyV1 'congestion.calculator.v2.Application.Services.TollFeeStrategyV1')
  - [#ctor(VehicleTollFeeStrategy,DateTollFeeStrategy)](#M-congestion-calculator-v2-Application-Services-TollFeeStrategyV1-#ctor-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy,congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy- 'congestion.calculator.v2.Application.Services.TollFeeStrategyV1.#ctor(congestion.calculator.v2.Application.Services.Interfaces.IVehicleTollFeeStrategy,congestion.calculator.v2.Application.Services.Interfaces.IDateTollFeeStrategy)')
  - [GetTollFee(vehicle,date)](#M-congestion-calculator-v2-Application-Services-TollFeeStrategyV1-GetTollFee-congestion-calculator-IVehicle,System-DateTime- 'congestion.calculator.v2.Application.Services.TollFeeStrategyV1.GetTollFee(congestion.calculator.IVehicle,System.DateTime)')
- [TollFreeVehicles](#T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1-TollFreeVehicles 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV1.TollFreeVehicles')
- [TollFreeVehicles](#T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2-TollFreeVehicles 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV2.TollFreeVehicles')
- [VehicleTollFeeStrategyV1](#T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV1')
  - [IsVehicleTollFree(vehicle)](#M-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1-IsVehicleTollFree-congestion-calculator-IVehicle- 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV1.IsVehicleTollFree(congestion.calculator.IVehicle)')
- [VehicleTollFeeStrategyV2](#T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV2')
  - [IsVehicleTollFree(vehicle)](#M-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2-IsVehicleTollFree-congestion-calculator-IVehicle- 'congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV2.IsVehicleTollFree(congestion.calculator.IVehicle)')

<a name='T-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository'></a>
## CSVTaxRuleRepository `type`

##### Namespace

congestion.calculator.v2.Infrastructure.Providers

##### Summary

Represents a repository for retrieving tax rules from a CSV file.

<a name='M-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository-#ctor-System-String-'></a>
### #ctor(filePath) `constructor`

##### Summary

Initializes a new instance of the CSVTaxRuleRepository class.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| filePath | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | The path to the CSV file containing tax rules. |

<a name='M-congestion-calculator-v2-Infrastructure-Providers-CSVTaxRuleRepository-GetAllRules-System-String-'></a>
### GetAllRules(city) `method`

##### Summary

Retrieves all tax rules for a specified city.

##### Returns

A list of TaxRuleDTO objects representing the tax rules for the specified city.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| city | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | The city for which to retrieve tax rules. |

<a name='T-congestion-calculator-CongestionTaxCalculator'></a>
## CongestionTaxCalculator `type`

##### Namespace

congestion.calculator

<a name='M-congestion-calculator-CongestionTaxCalculator-GetTax-congestion-calculator-IVehicle,System-DateTime[]-'></a>
### GetTax() `method`

##### Parameters

This method has no parameters.

<a name='T-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV1'></a>
## CongestionTaxCalculatorV1 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

This is the main class for CongestionTaxCalculator of a vehicle in several days

<a name='M-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV1-GetTax-congestion-calculator-IVehicle,System-DateTime[]-'></a>
### GetTax(vehicle,dates) `method`

##### Summary



##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') |  |
| dates | [System.DateTime[]](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime[] 'System.DateTime[]') |  |

<a name='T-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV2'></a>
## CongestionTaxCalculatorV2 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

This is the main class for CongestionTaxCalculator of a vehicle in several days
This new version added \`The single charge rule\`

<a name='M-congestion-calculator-v2-Application-Services-CongestionTaxCalculatorV2-GetTax-congestion-calculator-IVehicle,System-DateTime[]-'></a>
### GetTax(vehicle,dates) `method`

##### Summary

This method calculate total tax for a vehicle in several days and overall rules for different days
like 'The single charge rule' is implemented in this code. As this rule is a little general and vague,
in this version of \`CongestionTaxCalculatorV2\` in the first step all the date_times of every day based on
their [year,month,day] value will be grouped and then dates of a day will be ordered.
For every day, every date_time will be checked with all next ordered date_times and those which have less span 
than 60 minutes will be checked for maximum toll fee and the final value for this span will be the maximum value.
Then all of date_times in this span will be skipped, and this behavior will be repeated for next date_times after 
the span. The span maybe have just 1 date_time if there is no other date_time in its next 60 minutes, or maybe its 
length be 2...N, and then this N dates will be skipped for the next round.
Then, the final maximum toll fee for all 60 minutes spans will be summed and the minimum of total sum of this day 
and 60 -as the maximum toll fee in a day- will be considered for today. Then all toll fee of various days will be
summed and the total fee will be returned.

##### Returns



##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') |  |
| dates | [System.DateTime[]](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime[] 'System.DateTime[]') |  |

<a name='T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1'></a>
## DateTollFeeStrategyV1 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

The current date toll fee calculation strategy is implemented in this class

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1-GetDateTollFee-System-DateTime-'></a>
### GetDateTollFee(date) `method`

##### Summary

This method check a date and calculate its toll fee

##### Returns

the calculated toll fee value for the input date between 0 to int.MaxValue

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date for toll fee calculation |

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV1-IsTollFreeDate-System-DateTime-'></a>
### IsTollFreeDate(date) `method`

##### Summary

This method check a date that is toll free or not

##### Returns

true if the given date is toll free, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date |

<a name='T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2'></a>
## DateTollFeeStrategyV2 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

The current date toll fee calculation strategy is implemented in this class

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2-GetDateTollFee-System-DateTime-'></a>
### GetDateTollFee(date) `method`

##### Summary

This method check a date and calculate its toll fee

##### Returns

the calculated toll fee value for the input date between 0 to int.MaxValue

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date for toll fee calculation |

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV2-IsTollFreeDate-System-DateTime-'></a>
### IsTollFreeDate(date) `method`

##### Summary

This method check a date that is toll free or not.
List of National and Regional Public Holidays of Sweden in 2013:
https://www.calendarlabs.com/holidays/sweden/2013

##### Returns

true if the given date is toll free, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date |

<a name='T-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3'></a>
## DateTollFeeStrategyV3 `type`

##### Namespace

congestion.calculator.v2.Application.Services

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-#ctor-congestion-calculator-v2-Infrastructure-Repositories-ITaxRuleRepository,System-String-'></a>
### #ctor(taxRuleRepository,city) `constructor`

##### Summary

Constructor for DateTollFeeStrategyV3 class

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| taxRuleRepository | [congestion.calculator.v2.Infrastructure.Repositories.ITaxRuleRepository](#T-congestion-calculator-v2-Infrastructure-Repositories-ITaxRuleRepository 'congestion.calculator.v2.Infrastructure.Repositories.ITaxRuleRepository') | An object of ITaxRuleRepository used to retrieve tax rules |
| city | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | The city used to calculate toll fee |

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-GetDateTollFee-System-DateTime-'></a>
### GetDateTollFee(date) `method`

##### Summary

Calculates the toll fee based on the input date

##### Returns

The calculated toll fee for the input date

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The date used to calculate the toll fee |

<a name='M-congestion-calculator-v2-Application-Services-DateTollFeeStrategyV3-IsTollFreeDate-System-DateTime-'></a>
### IsTollFreeDate(date) `method`

##### Summary

This method check a date that is toll free or not.
List of National and Regional Public Holidays of Sweden in 2013:
https://www.calendarlabs.com/holidays/sweden/2013

##### Returns

true if the given date is toll free, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date |

<a name='T-congestion-calculator-v2-Domain-ValueObjects-Extensions'></a>
## Extensions `type`

##### Namespace

congestion.calculator.v2.Domain.ValueObjects

##### Summary

A dummy try to add ToTime method to static Convert class that was impossible now
even though it let other classes to convert strings to Time like:
(null as DateTime).ToTime("12:24")

<a name='T-congestion-calculator-v2-Application-Services-Interfaces-ICongestionTaxCalculatorStrategy'></a>
## ICongestionTaxCalculatorStrategy `type`

##### Namespace

congestion.calculator.v2.Application.Services.Interfaces

##### Summary

This interface let we implement the strategy design pattern for different congestion tax calculators

<a name='M-congestion-calculator-v2-Application-Services-Interfaces-ICongestionTaxCalculatorStrategy-GetTax-congestion-calculator-IVehicle,System-DateTime[]-'></a>
### GetTax(vehicle,dates) `method`

##### Summary

Every Congestion Tax Calculator should implement this method to calculate and return the tax for 
a vehicle in different days.
This method calculate total tax for a vehicle in several days and overall rules for different days
like 'The single charge rule' can be implemented in this part.

##### Returns

the tax value between 0 to int.MaxValue

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') |  |
| dates | [System.DateTime[]](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime[] 'System.DateTime[]') |  |

<a name='T-congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy'></a>
## IDateTollFeeStrategy `type`

##### Namespace

congestion.calculator.v2.Application.Services.Interfaces

##### Summary

This interface let the toll fee calculator to have different strategy for dates.

<a name='M-congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy-GetDateTollFee-System-DateTime-'></a>
### GetDateTollFee(date) `method`

##### Summary

Every toll fee strategy should implement this method to return the toll fee of the received date.

##### Returns

the toll fee value between 0 to int.MaxValue for the input date

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date to be checked for toll fee calculation |

<a name='T-congestion-calculator-v2-Application-Services-Interfaces-ITollFeeCalculatorStrategy'></a>
## ITollFeeCalculatorStrategy `type`

##### Namespace

congestion.calculator.v2.Application.Services.Interfaces

##### Summary

This interface is used to implement strategy design pattern for toll fee calculation

<a name='M-congestion-calculator-v2-Application-Services-Interfaces-ITollFeeCalculatorStrategy-GetTollFee-congestion-calculator-IVehicle,System-DateTime-'></a>
### GetTollFee(vehicle,date) `method`

##### Summary

Every toll fee calculator should implement this method to return the toll fee based on their strategy

##### Returns

the return value can be between 0 to int.MaxValue as the toll fee value

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') | this is the vehicle that its toll fee should be calculated |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | this is the day of toll fee calculation |

<a name='T-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy'></a>
## IVehicleTollFeeStrategy `type`

##### Namespace

congestion.calculator.v2.Application.Services.Interfaces

##### Summary

In our current toll fee calculator, the vehicle can be free of toll.
This interface is used to implement strategy design pattern for various vehicles toll fee calculation.

<a name='M-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy-IsVehicleTollFree-congestion-calculator-IVehicle-'></a>
### IsVehicleTollFree(vehicle) `method`

##### Summary

Every toll fee strategy should implement this method to return that is the vehicle fee of toll or not?

##### Returns

true if the vehicle is free of toll fee, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') | the vehicle to be checked for toll fee calculation |

<a name='T-congestion-calculator-v2-Application-Services-Interfaces-IVehicleV2'></a>
## IVehicleV2 `type`

##### Namespace

congestion.calculator.v2.Application.Services.Interfaces

##### Summary

This interface let us

<a name='T-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository'></a>
## MDTaxRuleRepository `type`

##### Namespace

congestion.calculator.v2.Infrastructure.Providers

##### Summary

Represents a repository for retrieving tax rules from a file.

<a name='M-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository-#ctor-System-String-'></a>
### #ctor(filePath) `constructor`

##### Summary

Initializes a new instance of the MDTaxRuleRepository class.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| filePath | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | The path to the file containing tax rules. |

<a name='M-congestion-calculator-v2-Infrastructure-Providers-MDTaxRuleRepository-GetAllRules-System-String-'></a>
### GetAllRules(city) `method`

##### Summary

Retrieves all tax rules for a specified city.

##### Returns

A list of TaxRuleDTO objects representing the tax rules for the specified city.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| city | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | The city for which to retrieve tax rules. |

<a name='T-congestion-calculator-v2-Application-Services-MainCongestionTaxCalculatorNew'></a>
## MainCongestionTaxCalculatorNew `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

This class uses Singleton design pattern to avoid user from instancing new dummy object for tax calculation.

<a name='T-congestion-calculator-v2-Domain-ValueObjects-Time'></a>
## Time `type`

##### Namespace

congestion.calculator.v2.Domain.ValueObjects

##### Summary

A class for representing a time of day.

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-Int64-'></a>
### #ctor(ticks) `constructor`

##### Summary

Initializes a new instance of the Time class using a number of ticks without 
considering the date part (year, month, day).

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| ticks | [System.Int64](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Int64 'System.Int64') | A number of ticks. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-Int32,System-Int32,System-Int32,System-Int32-'></a>
### #ctor(hour,minute,second,millisecond) `constructor`

##### Summary

Initializes a new instance of the Time class using hours, minutes, seconds, and milliseconds.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| hour | [System.Int32](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Int32 'System.Int32') | The hour component of the time. |
| minute | [System.Int32](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Int32 'System.Int32') | The minute component of the time. |
| second | [System.Int32](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Int32 'System.Int32') | The second component of the time. |
| millisecond | [System.Int32](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Int32 'System.Int32') | The millisecond component of the time. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-DateTime-'></a>
### #ctor(dt) `constructor`

##### Summary

Initializes a new instance of the Time class using a DateTime object.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| dt | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | A DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-#ctor-System-String-'></a>
### #ctor(timeString) `constructor`

##### Summary

Initializes a new instance of the Time class using a time string.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| timeString | [System.String](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.String 'System.String') | A string that represents a time in the format "hh:mm:ss.fff". |

<a name='P-congestion-calculator-v2-Domain-ValueObjects-Time-AsDateTime'></a>
### AsDateTime `property`

##### Summary

Gets or sets the time of day as a DateTime object.

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-CompareTo-congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### CompareTo(other) `method`

##### Summary

Compares the current Time object with another Time object.

##### Returns

A value that indicates the relative order of the Time objects being compared.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| other | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The Time object to compare with. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-CompareTo-System-DateTime-'></a>
### CompareTo(other) `method`

##### Summary

Compares the current Time object with a DateTime object.

##### Returns

A value that indicates the relative order of the Time and DateTime objects being compared.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| other | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The DateTime object to compare with. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-Equals-System-Object-'></a>
### Equals(obj) `method`

##### Summary

Determines whether the current Time object is equal to another object.

##### Returns

true if the current Time object is equal to the other object; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| obj | [System.Object](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.Object 'System.Object') | The object to compare with the current Time object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-GetHashCode'></a>
### GetHashCode() `method`

##### Summary

Returns a hash code for the current Time object.

##### Returns

A hash code for the current Time object.

##### Parameters

This method has no parameters.

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-ToString'></a>
### ToString() `method`

##### Summary

Returns a string that represents the current Time object in the format "hh:mm:ss.fff".

##### Returns

A string that represents the current Time object in the format "hh:mm:ss.fff".

##### Parameters

This method has no parameters.

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Equality-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_Equality(left,right) `method`

##### Summary

Determines whether two Time objects are equal.

##### Returns

true if the two Time objects are equal; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Equality-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_Equality(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the two objects are equal, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThan-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_GreaterThan(left,right) `method`

##### Summary

Determines whether one Time object is greater than another Time object.

##### Returns

true if the first Time object is greater than the second Time object; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThan-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_GreaterThan(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the left object is greater than the right object, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_GreaterThanOrEqual(left,right) `method`

##### Summary

Determines whether one Time object is greater than or equal to another Time object.

##### Returns

true if the first Time object is greater than or equal to the second Time object; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_GreaterThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_GreaterThanOrEqual(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the left object is greater than or equal to the right object, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Inequality-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_Inequality(left,right) `method`

##### Summary

Determines whether two Time objects are not equal.

##### Returns

true if the two Time objects are not equal; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_Inequality-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_Inequality(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the two objects are not equal, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThan-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_LessThan(left,right) `method`

##### Summary

Determines whether one Time object is less than another Time object.

##### Returns

true if the first Time object is less than the second Time object; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThan-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_LessThan(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the left object is less than the right object, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,congestion-calculator-v2-Domain-ValueObjects-Time-'></a>
### op_LessThanOrEqual(left,right) `method`

##### Summary

Determines whether one Time object is less than or equal to another Time object.

##### Returns

true if the first Time object is less than or equal to the second Time object; otherwise, false.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The first Time object to compare. |
| right | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The second Time object to compare. |

<a name='M-congestion-calculator-v2-Domain-ValueObjects-Time-op_LessThanOrEqual-congestion-calculator-v2-Domain-ValueObjects-Time,System-DateTime-'></a>
### op_LessThanOrEqual(left,right) `method`

##### Summary

This operator is used to compare a Time object with a DateTime object.

##### Returns

True if the left object is less than or equal to the right object, false otherwise.

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| left | [congestion.calculator.v2.Domain.ValueObjects.Time](#T-congestion-calculator-v2-Domain-ValueObjects-Time 'congestion.calculator.v2.Domain.ValueObjects.Time') | The initial Time object. |
| right | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | The second DateTime object. |

<a name='T-congestion-calculator-v2-Application-Services-TollFeeStrategyV1'></a>
## TollFeeStrategyV1 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

This is our first and current strategy for toll fee calculation of every vehicle in every date.

<a name='M-congestion-calculator-v2-Application-Services-TollFeeStrategyV1-#ctor-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy,congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy-'></a>
### #ctor(VehicleTollFeeStrategy,DateTollFeeStrategy) `constructor`

##### Summary

Here we use dependency injection strategy to get the toll fee calculation strategy for vehicles and dates

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| VehicleTollFeeStrategy | [congestion.calculator.v2.Application.Services.Interfaces.IVehicleTollFeeStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-IVehicleTollFeeStrategy 'congestion.calculator.v2.Application.Services.Interfaces.IVehicleTollFeeStrategy') | the strategy of vehicles for toll fee calculation |
| DateTollFeeStrategy | [congestion.calculator.v2.Application.Services.Interfaces.IDateTollFeeStrategy](#T-congestion-calculator-v2-Application-Services-Interfaces-IDateTollFeeStrategy 'congestion.calculator.v2.Application.Services.Interfaces.IDateTollFeeStrategy') | the strategy of dates for toll fee calculation |

<a name='M-congestion-calculator-v2-Application-Services-TollFeeStrategyV1-GetTollFee-congestion-calculator-IVehicle,System-DateTime-'></a>
### GetTollFee(vehicle,date) `method`

##### Summary

This method calculate the toll fee value for the given vehicle and date.

##### Returns

the calculated toll fee value for the input vehicle and date between 0 to int.MaxValue

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') | the input vehicle for toll fee calculation |
| date | [System.DateTime](http://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k:System.DateTime 'System.DateTime') | the input date for toll fee calculation |

<a name='T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1-TollFreeVehicles'></a>
## TollFreeVehicles `type`

##### Namespace

congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV1

##### Summary

This enum contains the names of current toll free vehicles based on this strategy
Convention: All names should be in Capital case

<a name='T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2-TollFreeVehicles'></a>
## TollFreeVehicles `type`

##### Namespace

congestion.calculator.v2.Application.Services.VehicleTollFeeStrategyV2

##### Summary

This enum contains the names of current toll free vehicles based on this strategy
Convention: All names should be in Capital case

<a name='T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1'></a>
## VehicleTollFeeStrategyV1 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

The current vehicle toll fee calculation strategy is implemented in this class

<a name='M-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV1-IsVehicleTollFree-congestion-calculator-IVehicle-'></a>
### IsVehicleTollFree(vehicle) `method`

##### Summary

This method check a vehicle to be toll free or not.

##### Returns

true if the input vehicle is free of toll fee, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') | the input vehicle for checking |

<a name='T-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2'></a>
## VehicleTollFeeStrategyV2 `type`

##### Namespace

congestion.calculator.v2.Application.Services

##### Summary

The current vehicle toll fee calculation strategy is implemented in this class
TODO: Code Review 29: This code is built after applying CR12, CR26, CR27, Please remove this line

<a name='M-congestion-calculator-v2-Application-Services-VehicleTollFeeStrategyV2-IsVehicleTollFree-congestion-calculator-IVehicle-'></a>
### IsVehicleTollFree(vehicle) `method`

##### Summary

This method check a vehicle to be toll free or not.

##### Returns

true if the input vehicle is free of toll fee, otherwise false

##### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| vehicle | [congestion.calculator.IVehicle](#T-congestion-calculator-IVehicle 'congestion.calculator.IVehicle') | the input vehicle for checking |
