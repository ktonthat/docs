page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.test.compute_gradient


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="/api_docs/python/tf/test/compute_gradient">
  <img src="https://www.tensorflow.org/images/tf_logo_32px.png" />
  TensorFlow 2 version</a>
</td>

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r1.15/tensorflow/python/ops/gradient_checker.py#L271-L335">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Computes and returns the theoretical and numerical Jacobian. (deprecated)

### Aliases:

* <a href="/api_docs/python/tf/test/compute_gradient"><code>tf.compat.v1.test.compute_gradient</code></a>


``` python
tf.test.compute_gradient(
    x,
    x_shape,
    y,
    y_shape,
    x_init_value=None,
    delta=0.001,
    init_targets=None,
    extra_feed_dict=None
)
```



<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use tf.test.compute_gradient in 2.0, which has better support for functions. Note that the two versions have different usage, so code change is needed.

If `x` or `y` is complex, the Jacobian will still be real but the
corresponding Jacobian dimension(s) will be twice as large.  This is required
even if both input and output is complex since TensorFlow graphs are not
necessarily holomorphic, and may have gradients not expressible as complex
numbers.  For example, if `x` is complex with shape `[m]` and `y` is complex
with shape `[n]`, each Jacobian `J` will have shape `[m * 2, n * 2]` with

    J[:m, :n] = d(Re y)/d(Re x)
    J[:m, n:] = d(Im y)/d(Re x)
    J[m:, :n] = d(Re y)/d(Im x)
    J[m:, n:] = d(Im y)/d(Im x)

#### Args:


* <b>`x`</b>: a tensor or list of tensors
* <b>`x_shape`</b>: the dimensions of x as a tuple or an array of ints. If x is a list,
then this is the list of shapes.
* <b>`y`</b>: a tensor
* <b>`y_shape`</b>: the dimensions of y as a tuple or an array of ints.
* <b>`x_init_value`</b>: (optional) a numpy array of the same shape as "x"
  representing the initial value of x. If x is a list, this should be a list
  of numpy arrays.  If this is none, the function will pick a random tensor
  as the initial value.
* <b>`delta`</b>: (optional) the amount of perturbation.
* <b>`init_targets`</b>: list of targets to run to initialize model params.
* <b>`extra_feed_dict`</b>: dict that allows fixing specified tensor values
  during the Jacobian calculation.


#### Returns:

Two 2-d numpy arrays representing the theoretical and numerical
Jacobian for dy/dx. Each has "x_size" rows and "y_size" columns
where "x_size" is the number of elements in x and "y_size" is the
number of elements in y. If x is a list, returns a list of two numpy arrays.