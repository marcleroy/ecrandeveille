---
title: 'Xamarin Forms, use C# to build views'
date: Sun, 08 Mar 2020 23:25:38 +0000
draft: false
tags: ['Code', 'Patterns']
---

MVVM problems

### ImmutableUI and TDD with Xamarin.Forms

* **Posted:** May 6, 2018
* **By:** Adam Pedley
* **In:** [Code](https://xamarinhelp.com/category/code/)

See [praeclarum](https://github.com/praeclarum)/**[ImmutableUI](https://github.com/praeclarum/ImmutableUI)**

and [adamped](https://github.com/adamped)/**[Pattern](https://github.com/adamped/Pattern)**

From

~~~htlm
![sss](https://xamarinhelp.com/wp-content/uploads/2017/01/xamarinhelp.png)
~~~

[https://xamarinhelp.com/wp-content/uploads/2017/01/xamarinhelp.png](https://xamarinhelp.com/wp-content/uploads/2017/01/xamarinhelp.png)

MVVM and XAML has failed me. A promise of abstracting to make reusable components, but they never get reused. Layers of complexity for virtually no benefit. If reuse is to happen as planned, it would require almost mystical level foresight into the future, across multiple projects. In the real world, our apps are self contained, and we don’t reuse.

We then code our views in XAML, but what has this given us? A way to neatly separate UI from code? But has it really? When you look at the converters, behaviors and more we need to keep coding, we keep building a bridge between C# and XAML. I have to write a converter, to do what is equivalent of ‘ != ‘ in C#. XAML is verbose and getting out of hand. Then I have to keep wiring up another property to send data back and forth between XAML and the ViewModel.

XAML was also meant to be done by designers, then passed to developers to wire up. I have never in my entire professional career ever seen this happen, and for many reasons, can never see it happening.

