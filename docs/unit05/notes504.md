---
layout: notes
title: "📓5.4: Accessors/Getters" 
parent: "5️⃣ Writing Classes"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 5.4](https://runestone.academy/ns/books/published/csawesome/Unit5-Writing-Classes/topic-5-4-accessor-methods.html?mode=browsing) 

---

## Accessor Methods (_Getters_)

Since the instance variables in a class are usually marked as ``private`` to the
class, if you want code outside the class to be able to access the value of an
instance variable, you need to write what is formally called an **accessor
methods** but which everyone actually just calls a **getter**. 

<div class="imp" markdown="block"> 
  
👉 A **getter** is a ``public`` method that _takes no arguments_ and _returns the value_ of the
``private`` instance variable. 

```java
class ExampleTemplate
{
  // Instance variable declaration
  private typeOfVar varName;

  // Accessor (getter) method template
  public typeOfVar getVarName()
  {
    return varName;
  }
}
```
</div>

---

## ⭐️ Summary


  

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome/index.html?mode=browsing).
{: .fs-2 }
