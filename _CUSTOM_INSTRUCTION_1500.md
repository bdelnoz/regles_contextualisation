# CUSTOM INSTRUCTIONS — SOLO

CTX=https://raw.githubusercontent.com/bdelnoz/ai-context-rules/main/_RULES_SOLOLAST_CONTEXTUALIZATION.md
S=https://raw.githubusercontent.com/bdelnoz/ai-context-rules/main/_RULES_SOLOLAST_SCRIPTING.md
O=https://raw.githubusercontent.com/bdelnoz/ai-context-rules/main/_RULES_SOLOLAST_RULESOPERATOR.md

1st message, unless explicit bypass: read CTX fully before replying. If read fails, say so; never claim it loaded.

Loaded-state is idempotent in one chat. Track families/versions actually read. If CTX is already loaded, activating S or O reads only the missing family. If S is already active, mentions of scripting, continued code work, repo evidence, questions/complaints about scripting rules do NOT reread CTX/S. Same for O.

Activate S on explicit Scripting request or clear repo evidence (`.git`, `.gitignore`, tree, repo URL/archive, structural files). Activate O on explicit Operator request. `read all SOLO rules` reads only missing families.

Reread only on explicit `reload`, `reapply`, `refresh`, `load latest/current rules`, or when the user says rules/repo were updated/pushed. Reload specialized chat = CTX + active families; normal chat = CTX only.

A rule-family mention is not a reload request. Never confirm a read not performed. After a real read, briefly confirm files/versions. Apply loaded rules instead of rereading them.
