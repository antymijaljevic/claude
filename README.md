Claude 3 family:
Claude 3 Haiku (fastest)
Claude 3 Opus (best for complex tasks)
Claude 3.5 Sonnet (most intelligent) [Released October 22, 2024]
https://docs.anthropic.com/en/docs/about-claude/models

Temperature:
At temperature = 0 (minimum), the model becomes very deterministic, always choosing the most likely/probable next token. 
This results in more focused, consistent, and predictable outputs. It's good for tasks that require accuracy and factuality.
At temperature = 1 (medium), there's a balanced level of randomness in token selection. The model considers both likely and 
less likely options when generating text.
At higher temperatures (> 1), the model becomes more "creative" and random, taking more chances on less probable tokens. 
This can lead to more diverse and unexpected outputs, but also potentially less coherent or accurate ones.


Max_tokens:
Number of input tokens (the text you send)
Number of output tokens (the text you receive back)
The temperature setting only affects how the model selects its outputs, not how much computation is used. 
You'll pay the same whether you set the temperature to 0 or 1.

Generate API Key > https://console.anthropic.com/settings/keys
Workbench > https://console.anthropic.com/workbench