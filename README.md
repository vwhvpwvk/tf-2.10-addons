# TensorFlow-2.10-Addons

-----------------

This is a fork to the depreciated "TensorFlow-Addons" library. This fork is meant to act as a helper library for the latest TensorFlow version (v2.10.1) for Windows native install. 

Pleaes refer to [README_orig.md](https://github.com/vwhvpwvk/tf-2.10-addons/README_orig.md) for the original README. 

**TensorFlow Addons** is a repository of contributions that conform to
well-established API patterns, but implement new functionality
not available in core TensorFlow. TensorFlow natively supports
a large number of operators, layers, metrics, losses, and optimizers.
However, in a fast moving field like ML, there are many interesting new
developments that cannot be integrated into core TensorFlow
(because their broad applicability is not yet clear, or it is mostly
 used by a smaller subset of the community).

## Addons Subpackages

* [tfa.activations](https://www.tensorflow.org/addons/api_docs/python/tfa/activations) 
* [tfa.callbacks](https://www.tensorflow.org/addons/api_docs/python/tfa/callbacks) 
* [tfa.image](https://www.tensorflow.org/addons/api_docs/python/tfa/image) 
* [tfa.layers](https://www.tensorflow.org/addons/api_docs/python/tfa/layers)
* [tfa.losses](https://www.tensorflow.org/addons/api_docs/python/tfa/losses)
* [tfa.metrics](https://www.tensorflow.org/addons/api_docs/python/tfa/metrics) 
* [tfa.optimizers](https://www.tensorflow.org/addons/api_docs/python/tfa/optimizers) 
* [tfa.rnn](https://www.tensorflow.org/addons/api_docs/python/tfa/rnn) 
* [tfa.seq2seq](https://www.tensorflow.org/addons/api_docs/python/tfa/seq2seq) 
* [tfa.text](https://www.tensorflow.org/addons/api_docs/python/tfa/text) 

## Maintainership
The maintainers of TensorFlow Addons can be found in the [CODEOWNERS](.github/CODEOWNERS) file of the repo. This file 
is parsed and pull requests will automatically tag the owners using a bot. If you would
like to maintain something, please feel free to submit a PR. We encourage multiple 
owners for all submodules.

## Installation
#### v.0.18.0

Matching verison of TF-addons for TensorFlow-2.10 is [v.0.18.0](https://github.com/tensorflow/addons/pull/2744). 

This repo aims to build upon the v.0.18.0 and add necessary functions as we go, for painless windows-native TensorFlow user experience.

We assum that miniconda3 is installed in windows, and TensorFlow 2.10.1 installed following the [official TensorFlow guide](https://www.tensorflow.org/install/pip#windows-native).

In Windows PowerShell, within the TensorFlow-2.10 conda environment:

```
git clone https://github.com/vwhvpwvk/tf-2.10-addons.git

cd tf-2.10-addons

."$env:CONDA_PREFIX\Scripts\pip" install . --no-cache-dir

```

Will install the current latest version of TensorFlow-addons to the conda environment:

```
tensorflow                2.10.1                   pypi_0    pypi
tensorflow-addons         0.18.0.dev0              pypi_0    pypi
```
To use TensorFlow Addons:

```python
import tensorflow as tf; import tensorflow_addons as tfa
tfa
```
```
>>> tfa
<module 'tensorflow_addons' from '[Project_dir]\\tf-2.10-addons\\tensorflow_addons\\__init__.py'>
```

### Python and C++ Op Compatility

This github repo is meant to build against tf-2.10. Please use compatible versions for other tf version.

#### Installing from Source (From original)

There is installing from source option, which I have not tried yet. It seems like the pip install within github repo works. 

##### GPU and CPU Custom Ops
```
git clone https://github.com/tensorflow/addons.git
cd addons

export TF_NEED_CUDA="1"

# Set these if the below defaults are different on your system
export TF_CUDA_VERSION="11"
export TF_CUDNN_VERSION="8"
export CUDA_TOOLKIT_PATH="/usr/local/cuda"
export CUDNN_INSTALL_PATH="/usr/lib/x86_64-linux-gnu"

# This script links project with TensorFlow dependency
python3 ./configure.py

bazel build build_pip_pkg
bazel-bin/build_pip_pkg artifacts

pip install artifacts/tensorflow_addons-*.whl
```

## Tutorials
See [`docs/tutorials/`](docs/tutorials/)
for end-to-end examples of various addons.

## License
[Apache License 2.0](LICENSE)