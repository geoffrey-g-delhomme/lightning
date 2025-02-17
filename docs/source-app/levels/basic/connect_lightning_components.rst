####################################################
Level 2: Connect components into a full stack AI app
####################################################

**Audience:** Users who want to build apps with multiple components.

**Prereqs:** You know how to `build a component <build_a_lightning_component.html>`_.

----

****************************
What is a full stack AI app?
****************************
In the ML world, workflows coordinate multiple pieces of code working together. In Lightning,
when we coordinate 2 or more `Lightning components <build_a_lightning_component.html>`_ working together,
we instead call it a Lightning App. The difference will become more obvious when we introduce reactive
workflows in the advanced section.

For the time being, we'll go over how to coordinate 2 components together in a traditional workflow setting
and explain how it works.

.. note:: If you've used workflow tools for Python, this page describes conventional DAGs.
        In `level 5 <../intermediate/run_lightning_work_in_parallel.html>`_, we introduce reactive workflows that generalize beyond DAGs
        so you can build complex systems without much effort.

----

***********
The toy app
***********

In this app, we define two components that run across 2 separate machines. One to train a model on a GPU machine and one to analyze the model
on a separate CPU machine. We save money by stopping the GPU machine when the work is done.

.. lit_tabs::
   :titles: Import Lightning; Define Component 1;  Define Component 2; Orchestrator; Connect component 1; Connect component 2; Implement run; Train; Analyze; Define app placeholder
   :descriptions: First, import Lightning; This component trains a model on a GPU machine; This component analyzes a model on a CPU machine; Define the LightningFlow that orchestrates components; Component 1 will run on a CPU machine; Component 2 will run on an accelerated GPU machine; Describe the workflow in the run method; Training runs first and completes; Analyze runs after training completes; This allows the app to be runnable
   :code_files: ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py
   :highlights: 2; 5-7; 9-11; 13; 16; 17; 19; 20; 21; 23
   :app_id: abc123
   :tab_rows: 4
   :height: 460px

|

Now run the app:

.. lit_tabs::
   :titles: Run on Lightning cloud; Your own hardware
   :descriptions: Run to see these 2 components execute on separate machines 🤯; Run it locally without code changes 🤯🤯;
   :code_files: ./hello_components/code_run_cloud.bash; ./hello_components/code_run_local.bash
   :tab_rows: 7
   :height: 195px

|

Now you can develop distributed cloud apps on your laptop 🤯🤯🤯🤯!


----

**************************
Now you know ...
**************************

Without going out of your way, you're now doing the following: (Hint: Click **visualize** to see an animation describing the code).

.. lit_tabs::
   :titles: Orchestration; Distributed cloud computing; Multi-machine communication; Multi-machine communication; Multi-cloud;
   :descriptions: Define orchestration in Python with full control-flow; The two pieces of independent Python code ran on separate machines 🤯🤯; The text "CPU machine 1" was sent from the flow machine to the machine running the TrainComponent;  The text "GPU machine 2" was sent from the flow machine to the machine running the AnalyzeComponent; The full Lightning app can move across clusters and clouds
   :code_files: ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./level_2_scripts/hello_app.py; ./hello_components/multi_cloud.bash
   :tab_rows: 4
   :highlights: 19-21; 16-17; 20; 21; 2, 6, 10
   :images: <img src="https://pl-bolts-doc-images.s3.us-east-2.amazonaws.com/orchestration.gif" style="max-height: 430px; width: auto"></img> | <img src="https://pl-bolts-doc-images.s3.us-east-2.amazonaws.com/distributed_computing.gif" style="max-height: 430px; width: auto"></img> | <img src="https://pl-bolts-doc-images.s3.us-east-2.amazonaws.com/multi_machine_comms.gif" style="max-height: 430px; width: auto"></img> | <img src="https://pl-bolts-doc-images.s3.us-east-2.amazonaws.com/multi_machine_comms.gif" style="max-height: 430px; width: auto"></img> | <img src="https://pl-bolts-doc-images.s3.us-east-2.amazonaws.com/multi_cloud.gif" style="max-height: 430px; width: auto"></img>
   :height: 450px

----

*********************
Maintain full control
*********************
Although we've abstracted the infrastructure, you still have full control when you need it:

.. lit_tabs::
   :titles: Scheduler; Crontab syntax; Auto-scaling; Organized Python; Full terraform control;
   :descriptions: Although you can use Python timers, we have a scheduler short-hand; You can also use full cron syntax; Code your own auto-scaling syntax (Lightning plays well with Kubernetes); *Remember* components organize ANY Python code which can even call external non-python scripts such as optimized C++ model servers ;Experts have the option to use terraform to configure Lightning clusters
   :code_files: ./level_2_scripts/hello_app_scheduler.py; ./level_2_scripts/hello_app_cron.py; ./level_2_scripts/hello_app_auto_scale.py; ./level_2_scripts/organized_app_python.py; ./level_2_scripts/tr.bash
   :tab_rows: 4
   :highlights: 24; 24; 21, 24, 27, 28; 9, 16, 17; 5
   :height: 680px

----

****************************************
Use your own orchestrator (experts only)
****************************************
If you have your own orchestrator, feel free to coordinate individual Lightning components with
those existing tools.

The Lightning orchestrator described below is optimized for advanced patterns using regular python
control-flow and an embedded state system that is discussed in the advanced sections.

To run the app from a CI/CD job, CLI or other orchestrators, run it without opening the UI (unless you need the UI)

.. code:: bash

    lightning run app app.py --open-ui=false

----

***************************
Next step: Build a real app
***************************
Now that you know how to build components and connect them, pick an app to build in a
step-by-step walkthrough.

Once you feel comfortable with these examples, move to the `intermediate levels <../intermediate/index.html>`_, where we'll learn about running
components in parallel so we can build reactive full-stack AI apps.

.. include:: basic_examples.rst
