# Assignment

## Run Tensorflow on the Cloud!
1. Create an AWS Account / Claim $100 Credit
    * [AWS Student Onboarding](https://drive.google.com/file/d/0B-EJQbRhH_OtR0l6bm1kT2hfenc/view?usp=sharing) 
    * __Note:__ AWS Account ID can be found at [AWS Billing Console](https://console.aws.amazon.com/billing/home?#/account)
1. Create a key pair:
    * [AWS Key Pair](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#KeyPairs:sort=keyName)
1. Launch Bitfusion AMI
    * [Launch AMI Guide](http://www.bitfusion.io/2016/05/09/easy-tensorflow-model-training-aws/)
    * __Notes:__ 
      * Pay attention to the price!
      * t1.micro instanced types are _free_ for 750 hours/month
      * After launching it may take up to 5 minutes before the Jupyter notebook is ready
1. Begin Assignment!

## Need to install julia?
After logging into Jupyter:
1. Create a new terminal window
    ![image](https://cloud.githubusercontent.com/assets/1668987/24310481/79a4fd4e-10a6-11e7-83c0-d46ebd7ed8ed.png)
1. Install julia with these commands (you may need to Ctrl+Shift+V) for paste:
    ```bash
    $ sudo add-apt-repository ppa:staticfloat/juliareleases
    $ sudo add-apt-repository ppa:staticfloat/julia-deps
    $ sudo apt-get update
    $ sudo apt-get install julia
    ````
1. Downgrade GMP [otherwise Julia throws errors](https://github.com/JuliaLang/julia/issues/12741)
    ````bash
    $ sudo apt-get install libgmp3-dev
    ````
1. Install IJulia from Julia REPL
    ````bash
    $ julia
    julia> Pkg.add("IJulia")
    ````
1. Install TensorFlow from Julia REPL
    ```bash
    julia> Pkg.add("TensorFlow")
    ```
1. Refresh Jupyter page and create a new Julia notebook!
    ![image](https://cloud.githubusercontent.com/assets/1668987/24311959/d15d0ab2-10ac-11e7-9787-594a60b3301a.png)
    
**NOTE** If you need to use the GPU for Julia, you will have to rebuild tensorflow to support CUDA 7.5 See [Guide](https://github.com/malmaud/TensorFlow.jl#installation)

## Worried about costs?
There is __[no way](https://forums.aws.amazon.com/thread.jspa?threadID=58127)__ to automatically limit your costs in AWS.

Costs incurred above the $100 credit are __automatically charged__ to your registered credit card!

Here are some tips to keep you under budget!

* __STOP__ Your instance when you're not using them
    * Do __NOT Terminate__, you will lose all your work.
    * Start them again when you want to work again. __Warning:__ IP address could change after restart!
    ![image](https://cloud.githubusercontent.com/assets/1668987/24265114/c976a346-0fd8-11e7-9bde-cf18cdd0680b.png)
* TERMINATE __only__ when all your data has been migrated out of the instance / you are finished with the assignment.
* Use [Billing Alarms](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-alarms) to warn you when you are close to using up all your $100 credit
* Create an Idle alarm to warn you if you forgot to stop the instance
    1. Select instance and create alarm
    ![image](https://cloud.githubusercontent.com/assets/1668987/24265190/0d1c6a86-0fd9-11e7-85c7-a71dd3858ee7.png)
    1. Create a topic to send yourself an email
    ![image](https://cloud.githubusercontent.com/assets/1668987/24264665/8f73565e-0fd7-11e7-9d31-4815ba0223ef.png)
    1. Set CPU Utilization level (Note: you can also automatically Stop Instance as well)
    ![image](https://cloud.githubusercontent.com/assets/1668987/24265020/8a7f030e-0fd8-11e7-9fd6-490524642155.png)
