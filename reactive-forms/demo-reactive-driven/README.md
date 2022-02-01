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
    - [Binding to Form Model](#binding-to-form-model)
    - [Accessing Model Properties](#accessing-model-properties)
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


### Binding to Form Model
By using [formgroup] you can bind the created FormGroup from the customer.component.ts

![Reactive Driven Form - Binding to Form](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingToForm.PNG)

And also bind the formControls to a specific created FormControl

![Reactive Driven Form - Binding controls](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingFormControl.PNG)


### Accessing Model Properties
You can acces the model properties 3 different ways.

![Reactive Driven Form - Accessing values](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

## Updating values

If you want to update all of the FormControls use setValue()

![Reactive Driven Form - setValue()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/SetValue.PNG)

If you want to update a part of the FormControls use patchValue()

![Reactive Driven Form - patchValue()](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

The third option is most usefull when controlls are refrenced frequently.
