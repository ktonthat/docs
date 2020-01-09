page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.framework.get_or_create_global_step


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r1.15/tensorflow/contrib/framework/python/ops/variables.py#L147-L158">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Returns and create (if necessary) the global step tensor. (deprecated)

``` python
tf.contrib.framework.get_or_create_global_step(graph=None)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please switch to tf.train.get_or_create_global_step

#### Args:


* <b>`graph`</b>: The graph in which to create the global step tensor. If missing, use
  default graph.


#### Returns:

The global step tensor.