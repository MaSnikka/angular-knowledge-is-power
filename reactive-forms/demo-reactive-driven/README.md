# Demo reactive driven

## Table of contents
- [Demo reactive driven](#demo-reactive-driven)
  - [Table of contents](#table-of-contents)
  - [Demo features](#demo-features)
  - [Using Reactive Forms](#using-reactive-forms)
  - [Concept](#concept)
  - [Form Model](#form-model)
    - [Form Group](#form-group)
    - [Form Controls](#form-controls)
      - [FormBuilder](#formbuilder)
    - [Binding to Form Model](#binding-to-form-model)
    - [Accessing Model Properties](#accessing-model-properties)
  - [Validation](#validation)
    - [Built-in validation rules](#built-in-validation-rules)
    - [Adjusting validation at Runtime](#adjusting-validation-at-runtime)
    - [Custom validators](#custom-validators)
    - [Custom validators with paramaters](#custom-validators-with-paramaters)
    - [Cross-field validation](#cross-field-validation)
  - [Updating values](#updating-values)

## Demo features

## Using Reactive Forms

Before you can use the Reactive Forms you need to import ReactiveFormsModule into the app.module.ts

![Reactive Driven Form - validation](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/ImportReactiveFormsModule.PNG)

## Concept
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/ReactiveFormsConcept.png)

## Form Model
The Form Model for controlling the form can contain the following:

![Reactive Driven Form - FormModel](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/FormModel.PNG)

### Form Group
![Reactive Driven Form - Create Form Group](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CreatingFormGroup.PNG)

### Form Controls
![Reactive Driven Form - Create Form Controls](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CreatingFormControls.PNG)

For a more readable constructor of the FormGroup use the FormBuilder
Import it.
![Reactive Driven Form - Import FormBuilder](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/FormBuilderImport.PNG)

Use it.
![Reactive Driven Form - Usage FormBuilder](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/FormBuilderUsage.PNG)

#### FormBuilder


### Binding to Form Model
By using [formgroup] you can bind the created FormGroup from the customer.component.ts

![Reactive Driven Form - Binding to Form](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingToForm.PNG)

And also bind the formControls to a specific created FormControl

![Reactive Driven Form - Binding controls](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingFormControl.PNG)


### Accessing Model Properties
You can acces the model properties 3 different ways.

![Reactive Driven Form - Accessing values](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

## Validation

### Built-in validation rules
These are the avaible validator options from the Validators class in Angular

![Reactive Driven Form - Validators class](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/Built-inValidatorsClass.PNG)

You can specify a validator in the FormBuilder like so:

![Reactive Driven Form - Build-in validators](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/Built-inValidators.PNG)

Import the validators:
![Reactive Driven Form - Import validators](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/ImportValidators.PNG)


### Adjusting validation at Runtime
Changing the validators of a FormControl can be done by using the setValidators() method.

![Reactive Driven Form - setValidators()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/SetValidators.PNG)

After setting new validators, you need to revalidate those validators  with updateValueAndValidity().

![Reactive Driven Form - updateValueAndValidity()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/updateValueAndValidity.PNG)

Here is an example of setting the phone field required when selecting notify via phone

![Reactive Driven Form - setNotifation()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AdjustingValidationComponent.PNG)

### Custom validators
Sometimes the built-in validators aren't what you are looking for. So lets just make a validator yourself!

A custom validator looks like this.
This will validate if there is a number input and if that number is between 1 and 5. Else it will return a valdiation error with the key 'rating'.
![Reactive Driven Form - Custom validator](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CustomValidatorRatingRange.PNG)

The return value can be used to display any validation error in the form.
![Reactive Driven Form - Display Error With Custom Validator](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CustomValidatorError.PNG)


And you add it the same way as a built-in validator.
![Reactive Driven Form - Add Custom Validator To FormBuilder](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/UsingCustomValidator.PNG)


### Custom validators with paramaters
And sometimes a custom validator without parameters isn't what you are looking for. So lets just make a validator with parameters!

Instead of returning the validation return a ValidatorFunction.

Here you can see the rewritten ratingRange function from the previous header.

![Reactive Driven Form - Custom Validator With Parameters](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/RatingRangeParameters.PNG)

Now it is possible to add parameters to the custom validation.

![Reactive Driven Form - Using Parameters in Custom Validator](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/UsingParamatersCustomValidator.PNG)

### Cross-field validation

## Updating values

If you want to update all of the FormControls use setValue()

![Reactive Driven Form - setValue()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/SetValue.PNG)

If you want to update a part of the FormControls use patchValue()

![Reactive Driven Form - patchValue()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

The third option is most useful when controlls are refrenced frequently.
