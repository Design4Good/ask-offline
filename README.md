# ask-offline

## Steps

1. Download [Ollama client](https://ollama.com/) [for Windows, size of EXE 700MB]
2. In command prompt, issue:
  ```ollama pull qwen2.5:1.5b``` or
  ```ollama pull llama-3.2:1b``` 
   
4. Fine-tune:  
  ```
  from peft import LoraConfig, get_peft_model
  from transformers import AutoModelForCausalLM, AutoTokenizer
  
  model_name = "gemma-2-2b"
  model = AutoModelForCausalLM.from_pretrained(model_name)
  tokenizer = AutoTokenizer.from_pretrained(model_name)
  
  config = LoraConfig(r=8, lora_alpha=16, lora_dropout=0.1)
  model = get_peft_model(model, config)
  ```
