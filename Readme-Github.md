# 1. Congestion Tax Calculator Assignment

Welcome to the Persici Financial Technologies assessment.

This repository contains a developer [assignment](ASSIGNMENT.md) used as a basis for candidate intervew and evaluation.

Clone this repository to get started. Due to a number of reasons, not least privacy, you will be asked to zip your solution and share it in, instead of submitting a pull-request.

# 1.1 Toll Fee Calculator

This is a C# module for calculating traffic toll fees for vehicles. It includes three interfaces and two classes.

## ITollFeeCalculator Interface
This interface defines what each toll fee calculator should do. It has a method called `GetTollFee` that calculates the toll fee for a vehicle on a specific date.

## IVehicleTollFeeStrategy Interface
This interface shows what each toll fee strategy should do to check whether a vehicle is toll-free or not. It has a method called `IsVehicleTollFree` that checks whether the vehicle should pay the toll fee or not.

## IDateTollFeeStrategy Interface
This interface helps calculate the toll fee for different dates. It has a method called `GetDateTollFee` that calculates the toll fee for a specific date.

## TollFeeStrategyV1 Class
This class implements all toll fee calculation solutions for each vehicle on each day. It takes two interfaces, `IVehicleTollFeeStrategy` and `IDateTollFeeStrategy`, as inputs and outputs. It has a method called `GetTollFee` that calculates the toll fee for a vehicle on a specific date. This class uses the strategy design pattern to implement toll fee strategies. For example, it uses the `IVehicleTollFeeStrategy` and `IDateTollFeeStrategy` interfaces to implement vehicle- and date-dependent toll fee strategies.


# Toll Fee Calculator
This code provides a toll fee calculator for different vehicles based on the strategy design pattern. The TollFeeStrategyV1 class is responsible for calculating the toll fee for a given vehicle and date.


# Congestion Tax Calculator
This code provides a toll fee calculator for different vehicles based on the strategy design pattern. The `TollFeeStrategyV1` class is responsible for calculating the toll fee for a given vehicle and date. The `VehicleTollFeeStrategyV1` class implements the `IVehicleTollFeeStrategy` interface and provides a method for checking whether a vehicle is toll-free or not. The `DateTollFeeStrategyV1` class implements the `IDateTollFeeStrategy` interface and provides a method for calculating the toll fee for a given date.

The `ICongestionTaxCalculator` interface lets us implement the strategy design pattern for different congestion tax calculators. The `CongestionTaxCalculatorV1` class implements the `ICongestionTaxCalculator` interface and provides a method for calculating the tax for a vehicle in different days based on the toll fee strategy.

The `CongestionTaxCalculator` static class provides a simple interface for accessing the `CongestionTaxCalculatorV1` implementation. It contains a single method, `GetTax`, which takes a vehicle and an array of dates and returns the total tax for those dates.

# 2. Usage

To use the `CongestionTaxCalculator`, simply call the `GetTax` method and pass in a vehicle and an array of dates:

```csharp
var vehicle = new Car();
var dates = new DateTime[] { DateTime.Parse("2023-07-06 06:00:00"), DateTime.Parse("2023-07-06 07:30:00") };
int tax = CongestionTaxCalculator.GetTax(vehicle, dates);
```

In the example above, we create a new Car instance and an array of dates. We then call the GetTax method of the CongestionTaxCalculator static class, passing in the vehicle and dates parameters. The method returns the total tax for those dates, which we store in the tax variable.

# 3. License
This code is licensed under the MIT license. See the LICENSE file for more information.