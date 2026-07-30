# Lab notes

## Statelessness
When I sent only the latest message, the model treated it as a fresh request and did not remember earlier turns. When I sent the full conversation history, it could stay consistent and respond with context, which shows that the chat is only memory-aware when we explicitly include prior messages in the `history` list.

## Temperature
A lower temperature such as `--temp 0.2` made the output more focused and predictable, while `--temp 1.3` made it more creative and varied. The higher setting was more likely to produce different wording or a less predictable response, even for the same prompt.

## Tokens
As prompts and conversations got longer, the amount of text sent to the model increased, so token usage also increased. In the chat loop, each turn sends the full accumulated history, which means longer conversations use more tokens and can cost more and take longer.

## Anything that surprised you or broke
The biggest surprise was that the model does not remember anything on its own unless we explicitly pass the prior messages. I also noticed that this code does not track tokens directly yet, so the effect of longer prompts is visible in the input size but not shown as an exact count until later parts of the lab.
