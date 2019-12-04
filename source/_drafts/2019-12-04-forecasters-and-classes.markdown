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

<style>
    p, blockquote, ul, ol, dl, li, table, pre {
    margin: 15px 0;
    }

    table {
    padding: 0;
    }

    table tr {
    border-top: 1px solid #cccccc;
    background-color: white;
    margin: 0;
    padding: 0;
    }

    table tr:nth-child(2n) {
    background-color: #f8f8f8;
    }

    table tr th {
    font-weight: bold;
    border: 1px solid #cccccc;
    text-align: center;
    margin: 0;
    padding: 6px 13px;
    }

    table tr td {
    border: 1px solid #cccccc;
    text-align: center;
    margin: 0;
    padding: 6px 13px;
    }

    table tr th :first-child, table tr td :first-child {
    margin-top: 0;
    }

    table tr th :last-child, table tr td :last-child {
    margin-bottom: 0;
    }
</style>


When we will use machine learning we have to do two things, they are split dataset into forecasters and classes, but how and why do that?

It is not properly necessary to do that, but it is easiest way to keep data on track and mitigate possible transformation on data that we do not want to changes.

But how to do that, firs of all we need to import a dataset:

I'll use iris dataset, but probably you will have you data coming from another source like SQL, csv, and many others...

--- 
<pre class="prettyprint">
    # Import modules that will be necessary.
    import pandas as pd
    import numpy as np
    from sklearn.datasets import load_iris

    # Import Iris dataset and transform into pandas Dataframe
    iris = load_iris()
    df = pd.DataFrame(data=np.c_[iris['data'], iris['target']],
                    columns=iris['feature_names']+['target'])
    df.head()
</pre>

<div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }

        .dataframe tbody tr th {
            vertical-align: top;
        }

        .dataframe thead th {
            text-align: center;
        }
    </style>
    <table border="1" class="dataframe">
        <thead>
            <tr style="text-align: center;">
            <th>0 - sepal length (cm)</th>
            <th>1 - sepal width (cm)</th>
            <th>2 - petal length (cm)</th>
            <th>3 - petal width (cm)</th>
            <th>4 - target</th>
            </tr>
        </thead>
        <tbody>
            <tr>
            <th>0</th>
            <td>5.1</td>
            <td>3.5</td>
            <td>1.4</td>
            <td>0.2</td>
            <td>0.0</td>
            </tr>
            <tr>
            <th>1</th>
            <td>4.9</td>
            <td>3.0</td>
            <td>1.4</td>
            <td>0.2</td>
            <td>0.0</td>
            </tr>
            <tr>
            <th>2</th>
            <td>4.7</td>
            <td>3.2</td>
            <td>1.3</td>
            <td>0.2</td>
            <td>0.0</td>
            </tr>
            <tr>
            <th>3</th>
            <td>4.6</td>
            <td>3.1</td>
            <td>1.5</td>
            <td>0.2</td>
            <td>0.0</td>
            </tr>
            <tr>
            <th>4</th>
            <td>5.0</td>
            <td>3.6</td>
            <td>1.4</td>
            <td>0.2</td>
            <td>0.0</td>
            </tr>
    </tbody>
    </table>
</div>

<pre class="prettyprint">
    forecasters = df.iloc[:, 0:4].values
    forecasters[0:5]
</pre>
    array([[5.1, 3.5, 1.4, 0.2],
        [4.9, 3. , 1.4, 0.2],
        [4.7, 3.2, 1.3, 0.2],
        [4.6, 3.1, 1.5, 0.2],
        [5. , 3.6, 1.4, 0.2]])
<pre class="prettyprint">
    classes = df.iloc[:, 4].values
    classes[0:5]
</pre>
    array([0., 0., 0., 0., 0.])

Explain code: 
I choose which columns I'll use as my features, they are in index:
- 0(sepal length (cm))
- 1(sepal width (cm))
- 2(petal length (cm))
- 3(petal width (cm))


And the last one is my class:
- 4(target).