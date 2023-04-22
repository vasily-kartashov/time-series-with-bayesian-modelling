On M1 mac, this is required to run Prophet: 

    CONDA_ENVS=$(conda info --envs | grep \* | awk '{print $NF}')
    ENV_NAME=time-series-with-bayesian-modelling
    cd "$CONDA_ENVS/envs/$ENV_NAME/lib/python3.10/site-packages"
    install_name_tool -add_rpath @executable_path/cmdstan-2.26.1/stan/lib/stan_math/lib/tbb prophet_model.bin

On M1 mac, this is required to run PyMC the first time:

    export LDFLAGS=-L/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/lib

Purge

    conda deactivate && conda remove -n time-series-with-bayesian-modelling --all

Initial setup with conda:

    conda env create --file environment.yml && conda activate time-series-with-bayesian-modelling

Upgrading dependencies:

    conda env update --file environment.yml --prune

Installing conda-tree:

    conda install -c conda-forge conda-tree

Checking dependencies:

    conda-tree depends -t numpy