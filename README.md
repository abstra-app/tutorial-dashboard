# Tutorial: Custom Dashboards in Abstra

Abstra forms are intentionally limited. These limitations help us maintain a **simple and consistent experience** when building dynamic forms.

However, it is not uncommon to need **fully custom interfaces** that go beyond what our standard widgets support, such as:

- [`MarkdownOutput`](https://www.abstra.io/docs/workflow/forms/widgets/markdown-output)
- [`HtmlOutput`](https://www.abstra.io/docs/workflow/forms/widgets/html-output)
- [`CustomInput`](https://www.abstra.io/docs/workflow/forms/widgets/custom-input)

> ⚠️ **Important:**  
> We strongly recommend trying to solve your use case using **HtmlOutput** or **CustomInput** before using the mechanism described below.  
>  
> The feature described here is **experimental** and **not yet fully battle-tested**.

---

# Extending Abstra with Custom Flask Routes

Applications built with Abstra run on top of a **Flask server**. Because of this, we provide a mechanism that allows you to **extend the application by registering custom routes**.

To do this, create a file named:

`__setup__.py`

Inside it, define a `setup` function:

```python
from flask import Blueprint

def setup(bp: Blueprint):
    # Add your custom routes here
    ...
```

The provided `Blueprint` can be used to register **fully custom endpoints and pages**.

This allows you to build **interfaces that are completely outside the standard Abstra widgets system**.

---

# Examples in This Repository

This repository contains **two example implementations** of this mechanism.

## 1. HTML Dashboards

Location:

`./dashboards`

This example demonstrates how to build **custom pages using HTML and CSS** to create dashboards.

## 2. Notebook Dashboards

Location:

`./notebooks`

This example demonstrates how to create **dashboard visualizations powered by Jupyter notebooks**.

---

# Notes

- You can import functions from the Abstra library normally, for example:

  - `abstra.messaging`
  - `abstra.common`
  - `abstra.tables`
  - `abstra.files`
  - and other Abstra modules.

- These custom pages **are not reflected inside the Abstra editor**.  
  As a result, the built-in **AI Chat assistant may not be aware of these capabilities or able to interact with them.**

---

# Support

If you decide to use this approach, **please notify your Abstra account manager** so we can provide the appropriate support.
