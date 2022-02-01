# Demo reactive driven

## Table of contents
- [Demo reactive driven](#demo-reactive-driven)
  - [Table of contents](#table-of-contents)
  - [Using Reactive Forms](#using-reactive-forms)
  - [Concept](#concept)
  - [Form Model](#form-model)
    - [Form Group](#form-group)
    - [Form Controls](#form-controls)
    - [Binding to Form Model](#binding-to-form-model)
    - [Accessing Model Properties](#accessing-model-properties)
  - [Demo features](#demo-features)

## Using Reactive Forms

Before you can use the Reactive Forms you need to import ReactiveFormsModule into the app.module.ts
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/ImportReactiveFormsModule.PNG)

## Concept
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/ReactiveFormsConcept.png)

## Form Model
The Form Model for controlling the form can contain the following:

![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/FormModel.PNG)

### Form Group
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CreatingFormGroup.PNG)

### Form Controls
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/CreatingFormControls.PNG)


### Binding to Form Model
By using [formgroup] you can bind the created FormGroup from the customer.component.ts
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingToForm.PNG)

And also bind the formControls to a specific created FormControl
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/BindingFormControl.PNG)


### Accessing Model Properties
You can acces the model properties 3 different ways.
![Template Driven Form - Variable input](https://gitlab.pp-dcs.nl/BasvE/angular-knowledge-is-power/-/raw/main/reactive-forms/demo-reactive-driven/images/AccessingModelProperties.PNG)

The third option is most usefull when controlls are refrenced frequently.


## Demo features
