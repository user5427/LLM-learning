# LLM Systems in the Real World

sequences for everything.

pastato vs pastato
vienas reiskia pastatas, pastato
kitas reiskia veiksmas, pastato

# Lost in the middle

Context rot - start and the end is remembered better than the middle. Context window length does not matter, it is still U shaped.

Accuracy is better when u mix documents in a random way than putting documents in some order on topic.

Compacting helps.

Treat the middle as cold zone.

## Things to keep in mind
- Position matters
- Order matters
- Framing of the question: "is this info correct?" vs "what is wrong here?" can change the answer.

- letter bias towards a-d answers
- Citations - order changes who gets cited
- Order changes accuracy


RAG pipeline failure modes:
- Missing retrieval
- Bad retrieval
- Conflicting retrieval
- Correct retrieval but ignored
- Right answer but wrong reason

COntrol it with:
- Prompting
- Logs
- Prioritization
- Evaluation of citations


It is not lying, just filling of text with plausible words.


## Limitations
- The prompt is not policy.
- Self report is not telemetry.

Keep in mind of failuers and log/backup/rollback everything.

Mix freedom with guardrails.
Prompt injections.


Lethal trifecta:
- Private data
- External communication
- Untrusted code

Evaluations can lie. Have a checlist.

## Cost influences design decisions

Prompt caching
