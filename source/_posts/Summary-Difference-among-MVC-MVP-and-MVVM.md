---
title: 'Summary: Difference among MVC, MVP and MVVM'
date: 2021-04-08 11:31:49
tags: Design pattern
---

This article is aimed to summarize three most popular design patterns: MVC, MVP, MVVM and weigh up the prons and cons among these three patterns.

---

#### MVC

MVC is the abbreviation of [Model-View-Controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller), which is commonly used for developing [user interfaces](https://en.wikipedia.org/wiki/User_interface) that divides the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user.

Here is the basic diagram of MCV pattern:

![](/images/400px-MVC-Process.svg.png)

- **Model**：The central component of the pattern. It is the application's dynamic data structure, independent of the user interface. It directly manages the data, logic and rules of the application.
- **View**：Any representation of information such as a chart, diagram or table. Multiple views of the same information are possible, such as a bar chart for management and a tabular view for accountants.
- **Controller**：Accepts input and converts it to commands for the model or view.

In a conclusion, basically the Controller is likewise a bridge, for it connects the View and Model which means transmits the data from model to view or some interactions that happens on View to Model.

Example：

![](/images/MVC-basic.svg.png)

So what's the advantages and disadvantages of MVC?

Firstly, the advantages I think that it's a more genetic way for us to use this, as MVC lasts for a long time, without any effort, we can surely develop any projects with MVC, like Android.

However, some drawbacks of MVC such as：

- the MVC doesn't quite match the principal of SOLID Design Principles, like Controller layer take responsible for View and Model.
- Codes become bloated in Controller layer when the projects get larger, it's not easy to seperate the codes readily and it makes automated unit testing difficult.

---

#### MVP

Base on MVC, MVP had been brought up to optimize the weaknesses of MVC. Definition of MVP from **Wikipedia** is：

> **Model–view–presenter** (**MVP**) is a derivation of the [model–view–controller](https://en.wikipedia.org/wiki/Model–view–controller) (MVC) [architectural pattern](https://en.wikipedia.org/wiki/Architectural_pattern), and is used mostly for building user interfaces.
>
> In MVP, the *presenter* assumes the functionality of the "middle-man". In MVP, all presentation logic is pushed to the presenter.

Diagram that depicts the Model View Presenter (MVP) GUI design pattern：

![](/images/Model_View_Presenter_GUI_Design_Pattern.png)

