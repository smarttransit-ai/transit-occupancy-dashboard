# Transit-occupancy-dashboard

If you do not have this environment then create it. To run just follow the instructions based on docker as described  below.

## Running app with Docker

```
docker build -t wegodash .
docker run --memory='4g' --rm -p 8080:8080 wegodash
```

Note we give 4 gigabyte to this. Make sure your docker dashboard has enough resources enabled. 

Go to your browser and open http://127.0.0.1:8080. It should look like below.

<img src="docs/dashboard.png"
     alt="Dashboard image"
     style="float: left; margin-right: 0px;" />




# Development instructions

Check your environments.

```bash
conda env list
```

Remove as needed.

```bash
conda --yes remove --name transit_dashboard --all
```
Create and activate the new environment.


```bash
conda create --name transit_dashboard python=3.8
conda activate transit_dashboard
```

Add the packages into the new environment.
It is tempting [to use pip](
https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#using-pip-in-an-environment).
It may be that some packages are not available in the main conda repositories for your platform.
In that case you may need to add additional channels.

```bash
# conda config --prepend channels conda-forge
conda config --set channel_priority false
conda install --yes --file requirements.txt
```

## converting between basic python and notebooks

use ipynb-py-convert

```bash
conda --yes install ipynb-py-convert
```

## Running app in development environment

```
conda activate transit_dashboard
cd app
python transitapp.py
```



