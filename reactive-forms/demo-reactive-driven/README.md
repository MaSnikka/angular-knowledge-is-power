# Demo reactive driven

## Table of contents
- [Demo reactive driven](#demo-reactive-driven)
  - [Table of contents](#table-of-contents)
  - [1. Demo features](#1-demo-features)
  - [2. Using Reactive Forms](#2-using-reactive-forms)
  - [3. Concept](#3-concept)
    - [Form Model](#form-model)
    - [Form Group](#form-group)
    - [Form Controls](#form-controls)
      - [FormBuilder](#formbuilder)
    - [Binding to Form Model](#binding-to-form-model)
    - [Accessing Model Properties](#accessing-model-properties)
  - [4. Updating values](#4-updating-values)
  - [5. Validation](#5-validation)
    - [Built-in validation rules](#built-in-validation-rules)
    - [Adjusting validation at Runtime](#adjusting-validation-at-runtime)
    - [Custom validators](#custom-validators)
    - [Custom validators with paramaters](#custom-validators-with-paramaters)
    - [Cross-field validation](#cross-field-validation)
  - [6. Reacting to changes](#6-reacting-to-changes)
    - [Watch](#watch)
    - [Reacht](#reacht)
    - [Reactive transformations](#reactive-transformations)

## 1. Demo features

## 2. Using Reactive Forms

Before you can use the Reactive Forms you need to import ReactiveFormsModule into the app.module.ts

![Reactive Driven Form - validation](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/ImportReactiveFormsModule.PNG)

## 3. Concept
![Template Driven Form - Variable input](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/ReactiveFormsConcept.png)

### Form Model
The Form Model for controlling the form can contain the following:

![Reactive Driven Form - FormModel](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/FormModel.PNG)

### Form Group
![Reactive Driven Form - Create Form Group](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/CreatingFormGroup.PNG)

### Form Controls
![Reactive Driven Form - Create Form Controls](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/CreatingFormControls.PNG)

For a more readable constructor of the FormGroup use the FormBuilder
Import it.

![Reactive Driven Form - Import FormBuilder](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/FormBuilderImport.PNG)

Use it.

![Reactive Driven Form - Usage FormBuilder](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/FormBuilderUsage.PNG)

#### FormBuilder


### Binding to Form Model
By using [formgroup] you can bind the created FormGroup from the customer.component.ts

![Reactive Driven Form - Binding to Form](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/BindingToForm.PNG)

And also bind the formControls to a specific created FormControl

![Reactive Driven Form - Binding controls](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/BindingFormControl.PNG)


### Accessing Model Properties
You can acces the model properties 3 different ways.

![Reactive Driven Form - Accessing values](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

## 4. Updating values

If you want to update all of the FormControls use setValue()

![Reactive Driven Form - setValue()](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/SetValue.PNG)

If you want to update a part of the FormControls use patchValue()

![Reactive Driven Form - patchValue()](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

The third option is most useful when controlls are refrenced frequently.

## 5. Validation

### Built-in validation rules
These are the avaible validator options from the Validators class in Angular

![Reactive Driven Form - Validators class](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/Built-inValidatorsClass.PNG)

You can specify a validator in the FormBuilder like so:

![Reactive Driven Form - Build-in validators](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/Built-inValidators.PNG)

Import the validators:

![Reactive Driven Form - Import validators](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/ImportValidators.PNG)


### Adjusting validation at Runtime
NOTE: Refer to Chapter 6 for reacting to changes in runtime

Changing the validators of a FormControl can be done by using the setValidators() method.

![Reactive Driven Form - setValidators()](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/SetValidators.PNG)

After setting new validators, you need to revalidate those validators  with updateValueAndValidity().

![Reactive Driven Form - updateValueAndValidity()](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/updateValueAndValidity.PNG)

Here is an example of setting the phone field required when selecting notify via phone

![Reactive Driven Form - setNotifation()](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/AdjustingValidationComponent.PNG)

### Custom validators
Sometimes the built-in validators aren't what you are looking for. So lets just make a validator yourself!

A custom validator looks like this.
This will validate if there is a number input and if that number is between 1 and 5. Else it will return a valdiation error with the key 'rating'.

![Reactive Driven Form - Custom validator](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/CustomValidatorRatingRange.PNG)

The return value can be used to display any validation error in the form.

![Reactive Driven Form - Display Error With Custom Validator](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/CustomValidatorError.PNG)


And you add it the same way as a built-in validator.

![Reactive Driven Form - Add Custom Validator To FormBuilder](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/UsingCustomValidator.PNG)


### Custom validators with paramaters
And sometimes a custom validator without parameters isn't what you are looking for. So lets just make a validator with parameters!

Here you can see the rewritten ratingRange function from the previous header.
Instead of returning the validation return a ValidatorFunction.

![Reactive Driven Form - Custom Validator With Parameters](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/RatingRangeParameters.PNG)

Now it is possible to add parameters to the custom validation.

![Reactive Driven Form - Using Parameters in Custom Validator](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/UsingParametersCustomValidator.PNG)

### Cross-field validation
There are use cases where you want to validate accross multiple fields for example, email confirmation.

This can be achieved with using nested FormGroups.

![Reactive Driven Form - Nested Group](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/NestedGroupValidation.PNG)

Here is an example of using a custom validator with a nested FormGroup. This function checks if the email value is the same as the confirm email value.

![Reactive Driven Form - Nested Group Custom Validation](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/NestedGroupCustomValidation.PNG)

This custom validator can be added to the nested FormGroup like so:

![Reactive Driven Form - Nested Form Group Add Custom Validation](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/NestedGroupAddCustomValidation.PNG)

Add customerForm.get('emailGroup').errors to the form to display the match error.

![Reactive Driven Form - Nested FormGroup Check Errors](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/NestedFormGroupCheckErrors.PNG)
out

This displays the following error message.

![Reactive Driven Form - Email Confirmation Error message](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/EmailConfirmationErrorMessage.PNG)
out

## 6. Reacting to changes

In this module I will go over the following topics
-Watch for user changes.
-React to those changes.
-Reactive transformations to improve how to watch the changes.

### Watch

You can subscribe to the valueChanges function of a FormControl, FormGroup or a Form itself. Below are some examples

![Reactive Driven Form - Email Confirmation Error message](https://raw.githubusercontent.com/MaSnikka/angular-knowledge-is-power/main/reactive-forms/demo-reactive-driven/images/Watching.PNG)

### Reacht

### Reactive transformations