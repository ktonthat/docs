page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# Module: tf.contrib.crf


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r1.15/tensorflow/contrib/crf/__init__.py">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



Linear-chain CRF layer.

<!-- Placeholder for "Used in" -->


## Classes

[`class CrfDecodeBackwardRnnCell`](../../tf/contrib/crf/CrfDecodeBackwardRnnCell): Computes backward decoding in a linear-chain CRF.

[`class CrfDecodeForwardRnnCell`](../../tf/contrib/crf/CrfDecodeForwardRnnCell): Computes the forward decoding in a linear-chain CRF.

[`class CrfForwardRnnCell`](../../tf/contrib/crf/CrfForwardRnnCell): Computes the alpha values in a linear-chain CRF.

## Functions

[`crf_binary_score(...)`](../../tf/contrib/crf/crf_binary_score): Computes the binary scores of tag sequences.

[`crf_decode(...)`](../../tf/contrib/crf/crf_decode): Decode the highest scoring sequence of tags in TensorFlow.

[`crf_log_likelihood(...)`](../../tf/contrib/crf/crf_log_likelihood): Computes the log-likelihood of tag sequences in a CRF.

[`crf_log_norm(...)`](../../tf/contrib/crf/crf_log_norm): Computes the normalization for a CRF.

[`crf_multitag_sequence_score(...)`](../../tf/contrib/crf/crf_multitag_sequence_score): Computes the unnormalized score of all tag sequences matching tag_bitmap.

[`crf_sequence_score(...)`](../../tf/contrib/crf/crf_sequence_score): Computes the unnormalized score for a tag sequence.

[`crf_unary_score(...)`](../../tf/contrib/crf/crf_unary_score): Computes the unary scores of tag sequences.

[`viterbi_decode(...)`](../../tf/contrib/crf/viterbi_decode): Decode the highest scoring sequence of tags outside of TensorFlow.