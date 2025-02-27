# vlmx
> [!CAUTION]
> This readme is primarily generated by a VLM (Claude 3.7 Sonnet).

Because it's 2025 and typing more than 4 letters is so 2024. Let VLMs do everything while you touch grass.

## 🌟 Features

- **Multi-Provider Support**: OpenAI, Claude, Gemini - we got 'em all
- **Context Magic**: Smart file handling that just works™
- **Artifact Handling**: Images, logs, code - vlmx remembers so you don't have to
- **In-Context Learning**: Show, don't tell (actually, let the VLM do both)
- **Tool Use**: Built-in Swiss Army knife for VLMs

## 🚀 Quick Start

```bash
git clone https://github.com/vlongle/vlmx.git
cd vlmx
conda create -n vlmx python=3.9
conda activate vlmx
pip install -e .
```

## 📖 Basic Usage

```python
from vlmx.agent import Agent, AgentConfig
from dotenv import load_dotenv
import os

# Load API key from .env file
load_dotenv()
API_KEY = os.environ.get('API_KEY')


SYSTEM_INSTRUCTION = "Do whatever I say correctly."

class HelperAgent(Agent):
    OUT_RESULT_PATH = "test.txt"

    def _make_system_instruction(self):
        return SYSTEM_INSTRUCTION

    def _make_prompt_parts(self, question: str):
        return question

    def parse_response(self, response):
        print("response:", response.text)
        ## string_to_file(response.txt, "path.txt")


# Initialize the agent
agent = HelperAgent(AgentConfig(
    model_name="gemini-2.0-flash-thinking-exp-01-21",
    out_dir="test_results",
    api_key=API_KEY
))

# Generate a prediction
response = agent.generate_prediction("What's 2+2?")
```

For more advanced features like context-aware agents, tool usage, and in-context learning, check out the `quickstart.ipynb` notebook in the repository.

## 📚 Documentation

We have no documentation because you can just ask the VLM to explain it to you.

## 🤝 Contributing

1. Fork it
2. Ask a VLM to code it
3. PR it
4. Profit?


## 📄 License

MIT License - Because sharing is caring, and VLMs care about everyone.