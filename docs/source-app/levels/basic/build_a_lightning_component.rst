##############################################
Level 1: Package code in a lightning component
##############################################

**Prereqs:** You know *basic* Python.

**Goal:** In this guide you'll learn to develop `a Lightning component <https://lightning.ai/components>`_.

.. join_slack::
   :align: left

----

*********************************
Why you need Lightning components
*********************************
A Lightning component organizes a piece of code into a self-contained, modular component that
can be integrated into your existing workflows or assembled to form a Lightning app.
A Lightning component manages its own infrastructure, auto-scaling, cost management, and more, so you
can focus on the program logic and not the cloud engineering.

Components run on the cloud or your laptop without code changes 🤯🤯. Connect components using your current workflow management tools or use
Lightning apps to build powerful sequential AND reactive workflows.

.. raw:: html

   <div style="display: flex; align-items: center; justify-content: center;">
      <img src="https://lightning-ai-docs.s3.amazonaws.com/intro_components.gif" style="max-width: 800px"></img>
   </div>

|

Organizing your code into Lightning components offers these benefits:

.. collapse:: Build systems not scripts

   |

   The Lightning structure forces best practices so you don't have to be an expert production engineer.
   Although it feels like you're writing a script, you are actually building a production-ready system.

.. collapse:: Cost control

   |

   The component run-time has been optimized for cost management to support the largest machine-learning workloads.
   Lower your cloud bill with machines that shut down or spin up faster.

.. collapse:: For beginners: Code like an expert

   |

   Lightning embeds the best practices of building production-ready full stack AI apps into your
   coding experience. You can write code like you normally do, and the Lightning structure
   ensures your code is implicitely production ready... even if you're just doing research.

.. collapse:: For experts: Scale with full control

   |

   if you know what you are doing, Lightning gives you full control to manage your own
   scaling logic, fault-tolerance and even pre-provisioning, all from Python. We even give you
   full flexibility to use tools like `terraform <../../cloud/customize_a_lightning_cluster.html>`_ to optimize cloud clusters for your Lightning apps.

.. collapse:: Integrate into your current workflow tools

   |

   Lightning components are self-contained pieces of funcionality. Add them to your current workflow
   tools to quickly fill in gaps in your ML workflow such as monitoring drift, training LLMs and more.
   You can (optionally) use the Lightning App to integrate components into a cohesive workflow.

.. collapse:: Packaged code

   |

   Lightning apps bundles components into an app that runs in any environment. The same code will run on your laptop,
   or any cloud or private clusters. You don't have to think about the cluster or know anything about the cloud.

.. collapse:: Rapid iteration

   |

   Iterate through ideas in hours not months because you don't have to learn a million other concepts that the components
   handle for you such as kubernetes, cost management, auto-scaling and more.

.. collapse:: Modularity

   |

   Components are modular and inter-operable by design. Leverage our vibrant community of components so you don't
   have to build each piece of the system yourself.

----

*****************
Install Lightning
*****************
First, install Lightning.

.. lit_tabs::
   :descriptions: Pip; Macs, Apple Silicon (M1/M2/M3); Windows
   :code_files: /install/pip.bash; /install/mac.bash; /install/windows.bash
   :tab_rows: 4
   :height: 180px

----

**************************
Build your first component
**************************
A Lightning component organizes Python code into a self-contained module so it can run on the cloud.

**Run one of these components!**

.. lit_tabs::
   :titles: Hello CPU world; Hello GPU (accelerated) world; Train PyTorch (cloud GPU); Train PyTorch with Lightning Trainer (cloud GPUs); Deploy a model on cloud GPUs; Run a model script; XGBoost; XGBoost (GPU accelerated); Build a streamlit demo
   :code_files: ./hello_components/hello_world.py; ./hello_components/hello_world_gpu.py; ./hello_components/train_pytorch.py; ./hello_components/train_ptl.py; ./hello_components/deploy_model.py; ./hello_components/run_script.py; ./hello_components/xgboost.py; ./hello_components/xgboost_gpu.py; ./hello_components/build_demo.py
   :highlights: 7; 10, 11; 3, 6;3;4;5; 6, 9; 15, 20, 21; 10, 14, 29
   :app_id: abc123
   :tab_rows: 4
   :height: 550px

|

Components run the same on the cloud and locally on your choice of hardware.

.. lit_tabs::
   :titles: Lightning Cloud (fully-managed); Your AWS account; Your own hardware
   :code_files: ./hello_components/code_run_cloud.bash; ./hello_components/code_run_cloud_yours.bash; ./hello_components/code_run_local.bash
   :tab_rows: 4
   :highlights: ; 5; 0
   :height: 195px

----

************
Key features
************
You now know enough to build a self-contained component that runs any Python code on the cloud that can be connected to form a
powerful Lightning app. Here are a few key features available to super-charge your work:

.. lit_tabs::
   :titles: 15+ accelerators; Auto-stop idle machines; Auto-timeout submitted work; Use spot machines (~70% discount); Work with massive datasets; Mount cloud storage; Use a custom container
   :code_files: ./key_features/accelerators.py; ./key_features/idle_machine.py; ./key_features/auto_timeout.py; ./key_features/spot.py; ./key_features/massive_dataset.py; ./key_features/mount_data.py; ./key_features/custom_container.py;
   :highlights: 11;11;11;11;11;2,7,10, 11; 11
   :app_id: abc123
   :tab_rows: 3
   :height: 430px

----

******************************
Use community-built components
******************************
Lightning has a vibrant collection of `community-built components <https://lightning.ai/components>`_ you can use as templates or to inspire you.


----

************************
Next: Connect components
************************
Now you can build components. To build powerful full stack AI apps you'll need to learn to connect them together.

.. raw:: html

    <div class="display-card-container">
        <div class="row">

.. Add callout items below this line

.. displayitem::
   :header: Level 2: Connect components
   :description: Learn to connect components
   :col_css: col-md-12
   :button_link: connect_lightning_components.html
   :height: 150
   :tag: beginner

.. raw:: html

        </div>
    </div>
