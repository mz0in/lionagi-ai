![PyPI - Version](https://img.shields.io/pypi/v/lionagi?labelColor=233476aa&color=231fc935) [![Downloads](https://static.pepy.tech/badge/lionagi/week)](https://pepy.tech/project/lionagi)

[PyPI](https://pypi.org/project/lionagi/) | [Documentation](https://lionagi.readthedocs.io/en/latest/) | [Discord](https://discord.gg/7RGWqpSxze)

  
# LionAGI
**Towards Automated General Intelligence**


LionAGI is a cutting-edge **intelligent agent framework**. It integrates data manipulation with advanced machine learning tools, such as Large Language Models (i.e. OpenAI's GPT). 
- Designed for data-centric, production-level projects,
- dramatically lowers the barrier in creating intelligent, automated systems
- that can understand and interact meaningfully with large volumes of data. 

Install LionAGI with pip:

```bash
pip install lionagi
```
Download the `.env_template` file, input your appropriate API_KEY, save the file, rename as `.env` and put in your project's root directory. 
by default we use `OPENAI_API_KEY`.

\*we now also supports all models in [OpenRouter](https://openrouter.ai/models)   (not released yet, you can have a preview in `main`)

\* https://lionagi.readthedocs.io/en/v0.0.111/ is the the latest stable, please `pip install lionagi==0.0.111` if you find 0.0.112 buggy 




### Features

- Robust performance
- Efficient data operations for reading, chunking, binning, writing, storing and managing data.
- Fast interaction with LLM services like OpenAI with **configurable rate limiting concurrent API calls** for maximum throughput. 
- Create a production ready LLM application **in hours**. Intuitive workflow management to streamline the process from idea to market.
- (Work In Progress): verstile intergration with most API and local LLM services.  

---
LionAGI is designed to be async only, please check python official documentation on how `async` work: [here](https://docs.python.org/3/library/asyncio.html)


**Notice**: 
* calling API with maximum throughput over large set of data with advanced models i.e. gpt-4 can get **EXPENSIVE IN JUST SECONDS**,
* please know what you are doing, and check the usage on OpenAI regularly
* default rate limits are set to be **tier 1** of OpenAI model `gpt-4-1104-preview`, please check the [OpenAI usage limit documentation](https://platform.openai.com/docs/guides/rate-limits?context=tier-free) you can modify token rate parameters to fit different use cases.
* if you would like to build from source, please download the [latest release](https://github.com/lion-agi/lionagi/releases),  **main is under development and will be changed without notice**


### Quick Start

The following example shows how to use LionAGI's `Session` object to interact with `gpt-4` model:

```python
import lionagi as li

# define system messages, context and user instruction
system = "You are a helpful assistant designed to perform calculations."
instruction = {"Addition":"Add the two numbers together i.e. x+y"}
context = {"x": 10, "y": 5}
```

```python
# in interactive environment (.ipynb for example)
calculator = li.Session(system=system)
result = await calculator.initiate(instruction=instruction,
                                   context=context,
                                   model="gpt-4-1106-preview")

print(f"Calculation Result: {result}")
```

```python
# or otherwise, you can use
import asyncio

async def main():
    calculator = li.Session(system=system)
    result = await calculator.initiate(instruction=instruction,
                                       context=context, 
                                       model="gpt-4-1106-preview")
    print(f"Calculation Result: {result}")

if __name__ == "__main__":
    asyncio.run(main())
```

Visit our notebooks for our examples. 

### Community

We encourage contributions to LionAGI and invite you to enrich its features and capabilities. Engage with us and other community members [Join Our Discord](https://discord.gg/7RGWqpSxze)

### Citation

When referencing LionAGI in your projects or research, please cite:

```bibtex
@software{Li_LionAGI_2023,
  author = {Haiyang Li},
  month = {12},
  year = {2023},
  title = {LionAGI: Towards Automated General Intelligence},
  url = {https://github.com/lion-agi/lionagi},
}
```

## Star History
![Star History Chart](https://api.star-history.com/svg?repos=lion-agi/lionagi&type=Date)

### Requirements
Python 3.9 or higher. 

