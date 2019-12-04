---
layout: post
title: "Forecasters and Classes"
author: "Oracy Martos"
date: 2019-12-04 16:28:19
modified_at: 2019-12-04 16:28:19
comments: true
image: https://res.cloudinary.com/dvy4tauff/image/upload/v1575487941/preview_forecasters_and_classes_ll9jsm.jpg
categories: wiki 
keywords: machine_learning, data_science 
---

When we will use machine learning we have to do two things, they are split dataset into forecasters and classes, but how and why do that?

It is not properly necessary to do that, but it is easiest way to keep data on track and mitigate possible transformation on data that we do not want to changes.

But how to do that, firs of all we need to import a dataset:

I'll use iris dataset, but probably you will have you data coming from another source like SQL, csv, and many others...

--- 

<pre class="prettyprint" style="border: none !important">
    <pre class="python">
    # Import modules that will be necessary.
    import pandas as pd
    from sklearn.datasets import load_iris
    
    # Import Iris dataset and transform into pandas Dataframe
    df = pd.DataFrame(load_iris().data, columns=load_iris()['feature_names'])

    df.head()
    <img src="/source/images/posts_images/df_head.png" alt="df_head">
    </pre>
</pre>

![df_head](/source/images/posts_images/df_head.png)