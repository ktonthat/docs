page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.recurrent.Recurrent


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r1.15/tensorflow/contrib/recurrent/python/ops/recurrent.py#L655-L742">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Compute a recurrent neural net.

``` python
tf.contrib.recurrent.Recurrent(
    theta,
    state0,
    inputs,
    cell_fn,
    cell_grad=None,
    extras=None,
    max_input_length=None,
    use_tpu=False,
    aligned_end=False
)
```



<!-- Placeholder for "Used in" -->

Roughly, Recurrent() computes the following:
  state = state0
  for t in inputs' sequence length:
    state = cell_fn(theta, state, inputs[t, :])
    accumulate_state[t, :] = state
  return accumulate_state, state

theta, state, inputs are all structures of tensors.

inputs[t, :] means taking a slice out from every tensor in the inputs.

accumulate_state[t, :] = state means that we stash every tensor in
'state' into a slice of the corresponding tensor in
accumulate_state.

cell_fn is a python callable computing (building up a TensorFlow
graph) the recurrent neural network's one forward step. Two calls of
cell_fn must describe two identical computations.

By construction, Recurrent()'s backward computation does not access
any intermediate values computed by cell_fn during forward
computation. We may extend Recurrent() to support that by taking a
customized backward function of cell_fn.

#### Args:


* <b>`theta`</b>: weights. A structure of tensors.
* <b>`state0`</b>: initial state. A structure of tensors.
* <b>`inputs`</b>: inputs. A structure of tensors.
* <b>`cell_fn`</b>: A python function, which computes:
  state1, extras = cell_fn(theta, state0, inputs[t, :])
* <b>`cell_grad`</b>: A python function which computes:
  dtheta, dstate0, dinputs[t, :] = cell_grad(
    theta, state0, inputs[t, :], extras, dstate1)
* <b>`extras`</b>: A structure of tensors. The 2nd return value of every
  invocation of cell_fn is a structure of tensors with matching keys
  and shapes of  this `extras`.
* <b>`max_input_length`</b>: maximum length of effective input. This is used to
  truncate the computation if the inputs have been allocated to a
  larger size. A scalar tensor.
* <b>`use_tpu`</b>: whether or not we are on TPU.
* <b>`aligned_end`</b>: A boolean indicating whether the sequence is aligned at
  the end.


#### Returns:

accumulate_state and the final state.