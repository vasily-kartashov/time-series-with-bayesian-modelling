On M1 mac, this is required to run Prophet: 

    cd $(poetry env info --path)/lib/python3.9/site-packages/prophet/stan_model
    install_name_tool -add_rpath @executable_path/cmdstan-2.26.1/stan/lib/stan_math/lib/tbb prophet_model.bin

