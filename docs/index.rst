LionAGI
#######
**Towards Automated General Intelligence**

LionAGI is a Python intelligent agent framework that combines data manipulation with AI tools, aiming to simplify the integration of advanced machine learning tools, such as Large Language Models (i.e. OpenAI's GPT), with production-level data-centric projects.

Install LionAGI with pip:

``pip install lionagi``

Download the ``.env_template`` file, input your OPENAI_API_KEY, save the file, rename as ``.env`` and put in your project's root directory. 

Features
********

- Robust performance. LionAGI is written in almost pure python. With minimum external dependency (``aiohttp``, ``httpx``, ``python-dotenv``, ``tiktoken``)
- Efficient data operations for reading, chunking, binning, writing, storing and managing data.
- Fast interaction with LLM services like OpenAI with **configurable rate limiting concurrent API calls** for maximum throughput.
- Create a production ready LLM application **in hours**. Intuitive workflow management to streamline and expedite the process from idea to market.

Currently, LionAGI only natively support OpenAI API calls, support for other LLM providers as well as open source models will be integrated in future releases. LionAGI is designed to be async only, please check python official documentation on `how async works <https://docs.python.org/3/library/asyncio.html>`_.


**Notice**: 

- calling API with maximum throughput over large set of data with advanced models i.e. gpt-4 can get **EXPENSIVE IN JUST SECONDS**,
- please know what you are doing, and check the usage on OpenAI regularly
- default rate limits are set to be **tier 1** of OpenAI model `gpt-4-1104-preview`, please check the `OpenAI usage limit documentation <https://platform.openai.com/docs/guides/rate-limits?context=tier-free)>`_ you can modify token rate parameters to fit different use cases.
- Documentation is under process


Quick Start
***********

The following example shows how to use LionAGI's ``Session`` object to interact with ``gpt-4`` model:

.. code-block:: python

  import lionagi as li

  # define system messages, context and user instruction
  system = "You are a helpful assistant designed to perform calculations."
  instruction = {"Addition":"Add the two numbers together i.e. x+y"}
  context = {"x": 10, "y": 5}

  # Initialize a session with a system message
  calculator = li.Session(system=system)

  # run a LLM API call
  result = await calculator.initiate(instruction=instruction,
                                     context=context)

  print(f"Calculation Result: {result}")

Visit our notebooks for our examples. 

Community
*********

We encourage contributions to LionAGI and invite you to enrich its features and capabilities. Engage with us and other community members on `Discord <https://discord.gg/ACnynvvPjt>`_

Citation
********

When referencing LionAGI in your projects or research, please cite:

.. code-block:: bibtex

  @software{Li_LionAGI_2023,
    author = {Haiyang Li},
    month = {12},
    year = {2023},
    title = {LionAGI: Towards Automated General Intelligence},
    url = {https://github.com/lion-agi/lionagi},
  }


Requirements
************
Python 3.9 or higher. 


.. toctree::
   :maxdepth: 1
   :caption: Get Started
   :hidden:

   Get_started/installation.rst
   Get_started/quick_start.rst
   Get_started/config.rst
   Get_started/Examples/index.rst

.. toctree::
   :maxdepth: 1
   :caption: API Reference
   :hidden:

   API_reference/utils_index.rst
   API_reference/session_index.rst
   API_reference/api_index.rst
