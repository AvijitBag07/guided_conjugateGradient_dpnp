# Intel® Python Data Parallel Extension for NumPy Getting Started Sample

The `Intel® Python DPNP Getting Started` sample code shows how to find conjugate gradient using the Intel Python API powered by the [Intel® Python DPNP - Data Parallel Extension for NumPy](https://github.com/IntelPython/dpnp).

| Area                   | Description
| :---                   | :---
| Category               | Getting Started
| What you will learn    | DPNP programming model for Intel GPU
| Time to complete       | 60 minutes
>**Note**: This sample is migrated from Cupy Python sample. See the [ConjugateGradient](https://github.com/cupy/cupy/blob/main/examples/cg/cg.py) sample in the cupy-samples GitHub.


## Purpose
The Data Parallel Extension for NumPy* (dpnp package) - a library that implements a subset of NumPy* that can be executed on any data parallel device. The subset is a drop-in replacement of core NumPy* functions and numerical data types. 

The DPNP is used to offload python code to INTEL GPU's. This is very similar to CUPY API [Comparsion_list](https://intelpython.github.io/dpnp/reference/comparison.html#).   


## Prerequisites

| Optimized for           | Description
| :---                    | :---
| OS                      | Ubuntu* 22.04 (or newer)
| Hardware                | Intel® Gen9 <br>Intel® Gen11 <br>Intel® Data Center GPU Max 
| Software                | Intel® Python Data Parallel Extension for NumPy (DPNP)
> **Note**: [Intel® Python DPNP - Data Parallel Extension for NumPy](https://github.com/IntelPython/dpnp).

## Key Implementation Details

- This get-started sample code is implemented for Intel GPUs using Python language. The example assumes the user has the latest DPNP installed in the environment, similar to what is delivered with the installation of the [Intel® Distribution for Python*](https://www.intel.com/content/www/us/en/developer/tools/oneapi/distribution-python-download.html).
  
## Environment Setup

You will need to download and install the following toolkits, tools, and components to use the sample.

**1. Intel Python**


Required Intel Python package: DPNP (Select Intel® Distribution for Python*: Offline on [Get Intel® Distribution for Python*](https://www.intel.com/content/www/us/en/developer/tools/oneapi/distribution-python-download.html) to install)


**2. (Offline Installer) Update the Intel Python base environment**

Load python env:
```
source $PYTHON_INSTALL/env/vars.sh
```
 
**3. (Offline Installer) Check the DPNP version**

```
python -c "import dpnp; print(dpnp.__version__)"
``` 
Note: if the version is 0.15.0 or more continue, otherwise need to upgrade the dpnp version 

**4. Clone the GitHub repository**
<!-- for oneapi-samples: git clone https://github.com/oneapi-src/oneAPI-samples.git
cd oneAPI-samples/DirectProgramming/<samples-folder>/<individual-sample-folder> -->
<!-- for migrated samples - provide git clone command for individual repo and cd to sample dir --> 
``` 
git clone https://github.com/oneapi-src/oneAPI-samples.git
cd oneAPI-samples/DirectProgramming/Python/DPNP_GettingStarted
```


## Run the Sample
>**Note**: Before running the sample, make sure Intel Python is installed.

1. Change to the sample directory.
2. Build the program.
   ```
   $ python cg.py
   ```

### AI Tools Offline Installer (Validated)  

**1. Register Conda kernel to Jupyter Notebook kernel**

If the default path is used during the installation of AI Tools:
```
$HOME/intel/oneapi/intelpython/envs/base/bin/python -m ipykernel install --user --name=base
```
If a non-default path is used:
```
<custom_path>/bin/python -m ipykernel install --user --name=base
```

**2. Launch Jupyter Notebook** 
<!-- add other flags to jupyter notebook command if needed, such as port 8888 or allow-root -->
```
jupyter notebook --ip=0.0.0.0
```
**3. Follow the instructions to open the URL with the token in your browser**

**4. Select the Notebook**
```
IntelPython_daal4py_GettingStarted.ipynb
```
**5. Change the kernel to `base`**
 
**6. Run every cell in the Notebook in sequence**

### Conda/PIP
> **Note**: Before running the instructions below, make sure your Conda/Python environment with AI Tools installed is activated

**1. Register Conda/Python kernel to Jupyter Notebook kernel** 
<!-- keep placeholders in this step, user could use any name for Conda/PIP env -->
For Conda:
```
<CONDA_PATH_TO_ENV>/bin/python -m ipykernel install --user --name=<your-env-name>
```
To know <CONDA_PATH_TO_ENV>, run `conda env list` and find your Conda environment path.

For PIP:
```
python -m ipykernel install --user --name=<your-env-name>
```
**2. Launch Jupyter Notebook**
<!-- add other flags to jupyter notebook command if needed, such as port 8888 or allow-root --> 
```
jupyter notebook --ip=0.0.0.0
```
**3. Follow the instructions to open the URL with the token in your browser**

**4. Select the Notebook**
```
IntelPython_daal4py_GettingStarted.ipynb
```
**5. Change the kernel to `<your-env-name>`**
<!-- leave <your-env-name> as a placeholder as user could choose any name for the env -->

**6. Run every cell in the Notebook in sequence**

### Docker
AI Tools Docker images already have Get Started samples pre-installed. Refer to [Working with Preset Containers](https://github.com/intel/ai-containers/tree/main/preset) to learn how to run the docker and samples.

## Example Output

```
Here's our model:

 NumberOfBetas: 14

NumberOfResponses: 1

InterceptFlag: False

Beta: array(
  [[ 0.00000000e+00 -1.05416344e-01  5.25259886e-02  4.26844883e-03
     2.76607367e+00 -2.82517989e+00  5.49968304e+00  3.48833264e-03
    -8.73247684e-01  1.74005447e-01 -8.38917510e-03 -3.28044397e-01
     1.58423529e-02 -4.57542900e-01]],
  dtype=float64, shape=(1, 14))

NumberOfFeatures: 13

Here is one of our loaded model's features:

 [[ 0.00000000e+00 -1.05416344e-01  5.25259886e-02  4.26844883e-03
   2.76607367e+00 -2.82517989e+00  5.49968304e+00  3.48833264e-03
  -8.73247684e-01  1.74005447e-01 -8.38917510e-03 -3.28044397e-01
   1.58423529e-02 -4.57542900e-01]]
[CODE_SAMPLE_COMPLETED_SUCCESFULLY]
```
## Related Samples

* [Intel® Python XGBoost* Getting Started Sample](https://github.com/oneapi-src/oneAPI-samples/tree/master/AI-and-Analytics/Getting-Started-Samples/IntelPython_XGBoost_GettingStarted)
* [Intel® Python Scikit-learn Extension Getting Started Sample](https://github.com/oneapi-src/oneAPI-samples/tree/master/AI-and-Analytics/Getting-Started-Samples/Intel_Extension_For_SKLearn_GettingStarted#intel-python-scikit-learn-extension-getting-started-sample)

## License

Code samples are licensed under the MIT license. See
[License.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/License.txt)
for details.

Third party program Licenses can be found here:
[third-party-programs.txt](https://github.com/oneapi-src/oneAPI-samples/blob/master/third-party-programs.txt)

*Other names and brands may be claimed as the property of others. [Trademarks](https://www.intel.com/content/www/us/en/legal/trademarks.html)
