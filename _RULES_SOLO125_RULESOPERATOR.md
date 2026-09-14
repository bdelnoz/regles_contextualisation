<!--
DOCUMENT INFORMATION
Document Name: _RULES_SOLO125_RULESOPERATOR.md
Version: SOLO125
Date / Time: 2026-09-14
Project: SOLO rules operator contextualization
Public status: GitHub-safe public rules file
Language: English
Short description: Rules for operating SOLO rule-maintenance chats, synchronized with CTX234 and SCRIPT413, with a mandatory commit-pinned CORE CHAIN plus the canonical 20-check FULL ACCEPTANCE validation for Operator/bootstrap/routing/delivery-rule changes.
-->

# _RULES_SOLO125_RULESOPERATOR.md

Canonical name: SOLO125 RULESOPERATOR  
Family: SOLOxxx RULESOPERATOR  
Current version: 125  
Document: _RULES_SOLO125_RULESOPERATOR.md  
Date: 2026-09-14  
Status: public, sanitized version 125 of the Operator rules file, synchronized with CTX234, SCRIPT413, and the Custom Instructions, with a CORE CHAIN pinned to the exact commit SHA and a mandatory canonical 20-check FULL ACCEPTANCE for Operator/bootstrap/routing/delivery changes.

These rules contextualize a chat dedicated to creating, modifying, correcting, versioning, documenting, and delivering SOLO rule files.

They define how a rules-operator chat must work. They do not replace the following rule families:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
```

------------------------------------------------------------------------

## 1. SCOPE

1. The RULESOPERATOR file applies to chats dedicated to SOLO rule maintenance.

2. It covers:
- creating new rules;
- modifying existing rules;
- correcting wording;
- versioning;
- updating local documentation;
- updating the local changelog;
- anti-regression checks;
- private-data leak checks;
- file delivery;
- preparation of ZIP packages.

3. It does not define the business/content rules of the global or scripting families.

4. It defines how the assistant must operate when the user provides rules to integrate.

------------------------------------------------------------------------

## 2. PUBLIC RULE FAMILIES

5. The three main families must remain separate:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

6. In the public `ai-context-rules` repository, only public RULES files from the active families are intended for publication.

7. The active public slots are:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

8. README files, CHANGELOG files, ZIPs, archives, internal documents, and private modules are local or delivery files, not public files to publish at repository root.

9. README and CHANGELOG files remain useful for delivery and local traceability, but they must be placed under `.docs/` or in a local delivery ZIP ignored by Git.

10. Public RULES files must not contain their own embedded changelog.

11. A public RULES file must contain active rules only, not detailed history of previous versions.

------------------------------------------------------------------------

## 3. CANONICAL PUBLIC REPOSITORY STRUCTURE

12. The canonical local repository is:

```text
/mnt/data2_78g/Security/scripts/Projects_web/ai-context-rules
```

13. The expected public root includes, in particular:

```text
AGENTS.md
CLAUDE.md -> AGENTS.md
AI_STUDYING_FILES/
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

14. The following folders and files are local or private and must not be published:

```text
*.zip
.tmp/
.old/
.private/
.docs/
_RULES_PRIVATE_*
uploads
*.pid
__pycache__
*.log
*.db
creation_log
*-swp
*.tmp
*.bak
logs/
output/
infos/
result/
results/
*.tar.gz
*.rar
certs/
secrets/
.secrets
.zip/
```

15. The project `.gitignore` structure must remain compatible with this public/local separation.

16. If a delivery contains README, CHANGELOG, or ZIP files, they may be delivered to the user but must not be treated as public repository-root files.

17. If a delivery is to be copied into the local repository, README and CHANGELOG files must go under `.docs/`, ZIPs may go under `.zip/` or remain ignored by `*.zip`, and private modules must remain under `.private/` or under the `_RULES_PRIVATE_*` pattern.

------------------------------------------------------------------------

## 4. PROHIBITION ON PRIVATE-DATA LEAKS

18. The three public RULES files must never contain unnecessary personal, family, medical, private, sensitive, nominative, or historical data.

19. This rule applies first and foremost to:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

20. Before producing or modifying a public RULES file, the assistant must perform an anti-leak check.

21. The anti-leak check must search for and exclude, in particular:
- names of private individuals;
- identifying family references;
- medical or health information;
- personal legal or administrative data;
- addresses, phone numbers, or private email addresses not explicitly intended for publication;
- details of personal conflicts;
- examples containing a real identifiable situation;
- internal histories containing sensitive data;
- old embedded changelogs containing private information.

22. If a useful rule contains private data, the assistant must generalize the public rule and move the private information to an appropriate local private file.

23. The assistant must not silently delete useful private information: it must extract it to an appropriate private file.

24. Private files must use a clear local name, for example:

```text
_RULES_PRIVATE_SOLOXXX_<MODULE>.md
```

25. Private files may also be organized under `.private/` when requested by the user or required by the local context.

26. Private files must never be included in a public package.

27. Public files must not cite the exact names of private modules if the name itself reveals sensitive information. They may cite the generic pattern `_RULES_PRIVATE_SOLOXXX_<MODULE>.md`.

28. If the user explicitly provides the name of a private module already present in the local repository, the assistant may use that name in a delivery response, but must avoid reintroducing it into a public rule if the name is sensitive.

------------------------------------------------------------------------

## 5. GO, APPROVAL, AND INTEGRATION

29. Without a clear GO, the assistant does not generate final files unless the user explicitly requests immediate execution.

30. When the user gives GO, the assistant produces the complete files directly.

31. GO may be expressed naturally: `go`, `go ahead`, `do the job`, `proceed`, `you can generate`, or equivalent.

32. After GO, the assistant must not ask for confirmation again for items already approved.

33. The user remains the final authority for approval, deletions, renames, private extractions, and version changes.

34. A discussion about a SOLO rule is working material for a file, not authorization for persistent memory, unless explicitly requested by the user.

------------------------------------------------------------------------

## 6. VERSIONING

35. Any real modification to a rules file must increment its version.

36. Any real modification to an associated local README or CHANGELOG must update its metadata.

37. The version number must be visible in:
- the filename when required by the naming convention;
- the header;
- the content;
- the local changelog.

38. Versions must remain traceable, but history must no longer be embedded in the public RULES file.

39. The detailed changelog must remain in the corresponding local CHANGELOG file, ideally under `.docs/` in the local repository.

40. If an intermediate version has no documented changelog, the assistant must state clearly that the changelog was not documented and must not invent history.

------------------------------------------------------------------------

## 7. NAMING

41. Active public patterns are:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.md
_RULES_SOLOXXX_SCRIPTING.md
_RULES_SOLOXXX_RULESOPERATOR.md
```

42. Local documentation patterns are:

```text
.docs/README_SOLOXXX_CONTEXTUALIZATION.md
.docs/CHANGELOG_SOLOXXX_CONTEXTUALIZATION.md
.docs/README_SOLOXXX_SCRIPTING.md
.docs/CHANGELOG_SOLOXXX_SCRIPTING.md
.docs/README_SOLOXXX_RULESOPERATOR.md
.docs/CHANGELOG_SOLOXXX_RULESOPERATOR.md
```

43. Local single-rule ZIP patterns are:

```text
_RULES_SOLOXXX_CONTEXTUALIZATION.zip
_RULES_SOLOXXX_SCRIPTING.zip
_RULES_SOLOXXX_RULESOPERATOR.zip
```

44. Local full-package patterns are:

```text
SOLOXXX_CONTEXTUALIZATION_PACKAGE.zip
SOLOXXX_SCRIPTING_PACKAGE.zip
SOLOXXX_RULESOPERATOR_PACKAGE.zip
```

45. Local private patterns are:

```text
_RULES_PRIVATE_SOLOXXX_<MODULE>.md
.private/<private_file>
```

46. The single-rule ZIP must have exactly the same basename as its `_RULES_...md` file, changing only `.md` to `.zip`.

47. The single-rule ZIP must contain only the corresponding rules file.

48. A complete family delivery package may contain:
- the public RULES file;
- the local README;
- the local CHANGELOG;
- the single-rule ZIP.

49. When the package is intended to be extracted into the local repository, README and CHANGELOG must be placed under `.docs/` inside the ZIP to avoid accidental publication.

------------------------------------------------------------------------

## 8. ANTI-REGRESSION AND ANTI-LEAK

50. No existing file may become smaller, summarized, impoverished, or simplified unless explicitly requested by the user.

51. A size reduction is allowed when it explicitly results from:
- private-data cleanup;
- externalization to a private file;
- removal of an embedded changelog;
- duplicate removal;
- a user-approved GitHub-safe restructuring.

52. Before delivery, the assistant must compare line and byte counts of modified files against their references.

53. If a modified file is shorter, the assistant must explain the exact reason for the reduction.

54. The anti-regression check must report:
- source file;
- produced file;
- old line count;
- new line count;
- old byte count;
- new byte count;
- status: OK, JUSTIFIED OK, or FAIL.

55. The anti-leak check must confirm that public files do not contain the private data targeted by the request.

56. If a block removed from the public file remains useful, it must exist in a local private file or local private archive.

57. The file supplied by the user or produced in the current chat is the source of truth.

58. The assistant must not reconstruct a complete supplied file from memory.

------------------------------------------------------------------------

## 9. FILE DELIVERY

59. For a SOLO-family modification, a delivery ZIP remains mandatory.

60. In the delivery response, present the complete package first, then any useful individual files.

61. For a public family in `ai-context-rules`, the normal delivery contains:

```text
_RULES_SOLOXXX_<FAMILY>.md
.docs/README_SOLOXXX_<FAMILY>.md
.docs/CHANGELOG_SOLOXXX_<FAMILY>.md
_RULES_SOLOXXX_<FAMILY>.zip
SOLOXXX_<FAMILY>_PACKAGE.zip
```

62. A public package must never include `.private/`, `.old/`, sensitive `.docs/`, `_RULES_PRIVATE_*`, or other private files unless the user explicitly requests a complete public+private package.

63. A local delivery package may contain `.docs/` so README and CHANGELOG remain outside GitHub publication.

64. If the user requests one ZIP containing everything, the assistant must state clearly whether the ZIP also contains private files.

------------------------------------------------------------------------

## 10. PRESENTATION OF MODIFICATIONS

65. When the user asks for a SOLO-rule modification, the assistant should by default present only the expected final result.

66. The assistant should not automatically display:
- the old rule;
- a before/after comparison;
- a diff;
- a long justification;
- a historical reconstruction;
- an explanation of every old wording.

67. Unless explicitly requested otherwise, show only:
- the complete corrected rule;
- the new block to integrate;
- the proposed final wording;
- new changes not yet approved.

68. If the user explicitly requests a comparison, audit, explanation, or before/after view, the assistant may show the old and new versions.

69. In a chat dedicated to creating, correcting, or maintaining SOLO rules, the default behavior is: final result first; comparison only on request.

------------------------------------------------------------------------

## 11. COMPLIANCE ERRORS AND RULE VIOLATIONS

70. If the user reports that a SOLO rule was not followed, the assistant must not immediately propose a new corrective rule.

71. It must first reread or search for the relevant existing rule in the supplied or active SOLO file.

72. It must identify the existing rule precisely: number, title, section, or relevant wording.

73. It must then state whether the error comes from a missing rule, an existing rule that is too vague, an existing rule that was not applied, or a misinterpretation of the rule.

74. If the existing rule already covers the problem, the assistant must not create a parallel rule.

75. If the existing rule already covers the problem, the assistant must propose a minimal correction to that rule, as an anti-regression sub-rule or a targeted clarification.

76. Before proposing any new rule, the assistant must display this mandatory template:

```text
existing rule found: yes / no
number or title of the relevant rule: <reference>
problem covered by the existing rule: yes / no
cause of the error: missing rule / rule too vague / existing rule not applied / misinterpretation
minimal proposed modification: <targeted correction>
```

77. The purpose is to prevent the assistant from inventing a corrective rule when a rule already exists but simply was not applied.

78. The assistant must not merely say that the user is right.

79. It must explain why the error occurred without inventing an unverified cause.

80. If the cause is scope confusion, it must say so clearly.

------------------------------------------------------------------------

## 12. CONTINUATION MODE

81. When a chat becomes too long, the assistant must propose a short continuation context rather than asking the user to paste the full export.

82. To continue in a new chat, the preferred flow is:
- provide the latest active files;
- provide a short continuation summary;
- avoid pasting the full raw history unless needed for an audit or bug report.

83. The full chat export is primarily for archiving, export debugging, or auditing.

84. It should not be pasted by default into a new working chat when active files and a summary are sufficient.

------------------------------------------------------------------------

## 13. SOLO105 ADDITION — GITHUB-SAFE STRUCTURE AND PUBLIC ANTI-LEAK

85. SOLO105 establishes the public/local-only structure of the `ai-context-rules` repository.

86. SOLO105 prohibits private data in the three public RULES files.

87. SOLO105 removes the embedded changelog from the public RULESOPERATOR file: detailed history lives in the corresponding local CHANGELOG file.

88. SOLO105 requires README and CHANGELOG files generated for deliveries to be treated as local documentation or delivery artifacts, not as public repository-root files.

89. SOLO105 requires any sensitive content extracted from a public file to be preserved in a local private file when still useful.

90. SOLO105 requires the public/local separation to be checked before delivery: public root for public RULES, `.docs/` for local documentation, `.private/` or `_RULES_PRIVATE_*` for private content, and ZIPs ignored by Git.

------------------------------------------------------------------------

## 14. SOLO111 ADDITION — HUMAN-READABLE TITLES FOR ACTIVE CHATS OF ALL TYPES

91. The active-chat title convention is no longer limited to SOLO Operator chats.

92. It applies to any chat currently used for an active workflow: Operator, contextualization, scripting, extension development, debugging, feature request, publication, packaging, documentation, or another technical project.

93. The assistant must not claim it can rename the chat automatically unless the ChatGPT interface explicitly gives it that capability.

94. When a new active working chat is created, or a chat becomes the current chat for a workflow, the assistant must propose a short, sortable title ready to copy and paste.

95. The canonical prefix for currently active chats is:

```text
000. <readable type> +++
```

96. `000.` means: current, priority, or actively used chat.

97. `<readable type>` must appear immediately after `000.` so the chat list remains human-readable.

98. `+++` remains the visual and quick-search marker in ChatGPT, but it comes after the readable type.

99. Recommended canonical pattern:

```text
000. <readable_type> +++<TECH_TYPE>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

100. Recommended examples:

```text
000. operator +++OP113_CTX231_S409_20260802
000. extension +++EXTBR_VOICECONTROL_DEBUG_20260726
000. scripting +++SCRIPT_FIREWALL_CTX231_S409_20260802
000. docs +++README_REPO_CONTEXT_RULES_20260726
```

101. Older chats, drafts, archives, or non-current chats may keep titles using `001.`, `002.`, `003.`, or equivalent.

102. The title is normally set when the chat is created or promoted to active status. The assistant must not ask to rename the chat after every small change.

103. If a major reference version changes during the chat and the user intends to continue in that chat for a long time, the assistant may propose an updated title, but must not impose it.

104. In a new Operator chat, as soon as the user says the chat is intended to modify SOLO rules, the assistant must provide:
- confirmation of the Operator role;
- known active versions;
- a proposed readable canonical title;
- a reminder that the user must rename the chat manually if the interface does not allow the assistant to do so.

105. The chat title must never contain personal, private, medical, family, sensitive, nominative, insulting data, a sensitive local path, secret, token, private URL, or other non-public information.

------------------------------------------------------------------------

## 15. SOLO107 ADDITION — DELIVERY ZIP LOCK

106. Before delivering a ZIP, the assistant must verify that the ZIP file actually exists in the sandbox or active working environment.

107. The assistant must never provide a link to an assumed ZIP that has not been created or confirmed.

108. Before delivery, the assistant must inspect the ZIP contents by listing the embedded files.

109. For a single-rule ZIP, the internal contents must be exactly the corresponding `_RULES_...md` file and nothing else.

110. For a complete SOLO-family package, the contents must follow the expected structure: public RULES file, local README under `.docs/` when applicable, local CHANGELOG under `.docs/` when applicable, and the single-rule ZIP.

111. For a public package, the assistant must verify that no `.private/`, `_RULES_PRIVATE_*`, `.old/`, sensitive archive, or explicitly private content is included.

112. If the user explicitly requests a complete public+private ZIP, the assistant may include `.private/`, but must state this clearly in the delivery response.

113. If ZIP validation fails, the assistant must fix the ZIP before delivery or clearly state that the ZIP delivery is invalid.

------------------------------------------------------------------------

## 16. SOLO111 ADDITION — CANONICAL REPOSITORY DELIVERY STRUCTURE, `.gitignore`, AND NAME-BASED CONFIDENTIALITY

114. The current canonical structure of `ai-context-rules` must be respected for every SOLO delivery.

115. The expected public root contains:

```text
AGENTS.md
CLAUDE.md -> AGENTS.md
README.md
_CUSTOM_INSTRUCTIONS.md
_RULES_SOLOxxx_CONTEXTUALIZATION.md
_RULES_SOLOxxx_SCRIPTING.md
_RULES_SOLOxxx_RULESOPERATOR.md
_RULES_SOLOLAST_CONTEXTUALIZATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
AI_STUDYING_FILES/
```

116. The public `AI_STUDYING_FILES/` folder may contain study documents, notes, templates, AI questions/answers, feature-request resources, or other intentionally publishable material.

117. The presence of `AI_STUDYING_FILES/` in the public repository is allowed when the user confirms it is intentional.

118. The public rule files publishable at repository root are only the active versioned public families and their generic `SOLOLAST` copies.

119. The following generic pattern may be cited publicly to document Git exclusion:

```text
_RULES_PRIVATE_*
```

120. `_RULES_PRIVATE_*` is allowed in `.gitignore`, public rules, and the README when used only to document a generic exclusion or confidentiality rule.

121. The exact real names of private files must not appear in public files, the public README, public examples, public packages, or the GitHub remote.

122. In particular, the assistant must avoid publishing a private filename that reveals the exact private subject after the generic prefix.

123. Local private files may remain at local repository root if `_RULES_PRIVATE_*` properly covers them in `.gitignore`.

124. `.private/` may exist even when empty. Private files do not have to be moved there if the user chooses to keep them at local root while excluding them from Git.

125. The following local folders and files must remain unpublished:

```text
.docs/
.old/
.private/
.zip/
.tmp/
*.zip
_RULES_PRIVATE_*
```

126. Delivery README and CHANGELOG files must not be placed at public root. They must be placed under:

```text
.docs/
```

127. All ZIP files generated for a SOLO delivery must be placed under:

```text
.zip/
```

128. This applies to single-rule ZIPs, per-family packages, and complete internal bundles.

129. A full-export ZIP may be downloaded to repository root and extracted with “extract here.” Its content must be organized so files land directly in the correct locations.

130. Depending on the families delivered, the full-export ZIP must contain at minimum:
- public `_RULES_SOLO...md` files at root;
- public `_RULES_SOLOLAST_...md` files at root;
- `README.md` if updated;
- `.gitignore`;
- delivery README and CHANGELOG files under `.docs/`;
- all ZIP files under `.zip/`.

131. The full-export ZIP must not publish private content that was not requested. Local private files may be included only in an explicitly requested private or full public/private export.

132. For every new SOLO version or delivery, the assistant must provide `.gitignore`, even if its contents are unchanged.

133. The delivered `.gitignore` acts as an anti-regression safeguard against:
- accidental modification by a script;
- a badly placed ZIP extraction;
- manual copying;
- accidental removal of an exclusion;
- a future leak of private files or ZIPs.

134. The minimum expected `.gitignore` content must include at least:

```text
*.zip
.tmp/
.old/
.private/
.docs/
_RULES_PRIVATE_*
logs/
output/
infos/
result/
results/
*.tar.gz
*.rar
certs/
secrets/
.secrets
.zip/
```

135. Making `.gitignore` locally read-only with `chmod 444 .gitignore` is acceptable after validation, but Git does not reliably preserve that read-only bit across machines.

136. The stronger local lock `chattr +i .gitignore` may be used after final push if the user chooses, but the assistant must not apply it automatically.

137. When an older delivery rule conflicts with this structure, the newer applicable rule prevails.

138. Before delivery, the assistant must verify:
- single-rule ZIP: contains only its `_RULES_...md`;
- family package: contains the RULES file at root, `.docs/README...`, `.docs/CHANGELOG...`, `.zip/_RULES_...zip`;
- full package: contains only the requested public files and expected local artifacts;
- no exact real private filename appears in delivered public files.

------------------------------------------------------------------------

## 17. SOLO111 ADDITION — GENERIC SOLOLAST FILES FOR AUTOMATIC LOADING

129. With every SOLO delivery, the assistant must provide the usual versioned files plus the stable generic `SOLOLAST` copies for the delivered families.

130. Expected generic public files are:

```text
_RULES_SOLOLAST_CONTEXTUALIZATION.md
_RULES_SOLOLAST_RULESOPERATOR.md
_RULES_SOLOLAST_SCRIPTING.md
```

131. Each `SOLOLAST` file must be a copy of the latest active version of its family.

132. A `SOLOLAST` file is not a new rule family. It is a stable-name distribution alias for the latest active public rules.

133. The internal content of a `SOLOLAST` file may keep the source version metadata. The assistant must not artificially rewrite the header as version `SOLOLAST` when a simple copy is requested.

134. Purpose: allow Custom Instructions or any other external mechanism to point to stable GitHub URLs without changing filenames on every version increment.

135. If a delivery concerns only one SOLO family, the assistant must provide at least that family’s `SOLOLAST` file.

136. If a delivery concerns all three public families, provide all three `SOLOLAST` files.

137. Public `SOLOLAST` files must never be created from memory. They must be copied from the versioned file actually generated or supplied in the current chat.

138. Before delivery, verify that each delivered family’s `SOLOLAST` file actually exists and matches the announced latest active version.

139. In an extract-here-ready delivery for `ai-context-rules`, `SOLOLAST` files must be placed at repository root alongside the versioned `_RULES_SOLOxxx_...md` files.

140. `SOLOLAST` files must not replace the versioned files. Both forms must coexist: versioned for history, generic for automatic loading.

141. Public packages must never include private files merely for the purpose of creating or synchronizing `SOLOLAST`.

------------------------------------------------------------------------

142. When a delivery changes an active family, the public README must be checked and updated if versions, public structure, active filenames, or public usage have changed.

143. The public README must not cite exact real private filenames. It may cite only the generic `_RULES_PRIVATE_*` pattern when needed to document Git exclusion.

------------------------------------------------------------------------

## 18. OPERATIONAL SUMMARY

144. The three public RULES files must remain clean, generalized, and publishable.

145. Private data must remain local and ignored by Git.

146. The generic `_RULES_PRIVATE_*` pattern is allowed in `.gitignore` and public rules when documenting a generic exclusion.

147. Exact real private filenames must not be published in the remote, README, public rules, public examples, or public packages.

148. Changelogs must not be embedded in public RULES files.

149. Delivery README and CHANGELOG files must remain under `.docs/`.

150. All delivery ZIPs must remain under `.zip/`.

151. `.gitignore` must be included with every SOLO delivery.

152. `.gitignore` may be protected locally as read-only after validation, but that protection is not a portable Git guarantee.

153. The public README must remain synchronized with active versions, `SOLOLAST` files, and the current public structure.

154. Every active chat must receive a short, searchable title according to the active `000. <readable type> +++...` convention.

155. When the user reports a rule violation, the assistant must first inspect the relevant existing rule before proposing a new rule.

156. Before delivery, ZIPs must actually be created, validated, and listed, with no phantom links or accidental private content.

157. With every SOLO delivery, versioned files remain the historical reference and `SOLOLAST` files serve as stable public aliases.

158. Base rule: public material must be generic; private material must remain local, hidden behind a generic pattern, and ignored by Git.

------------------------------------------------------------------------

## 19. SOLO111 ADDITION — CLOSING AN OVERLONG OPERATOR CHAT AND MOVING TO A NEW CHAT

159. When an Operator chat becomes too long, the assistant must prepare a usable closing handoff rather than continue accumulating history.

160. The closing handoff must produce or recall:
- final active versions;
- delivered files;
- corrected points;
- checks performed;
- any remaining points to verify;
- a short resume context for the next Operator chat.

161. The resume context must be short, operational, and copyable into the new chat.

162. It must not contain exact real private filenames.

163. It must state the active title convention, `SOLOLAST` files, current public structure, and the confidentiality criterion approved by the user.

164. If the user opens a new Operator chat, the assistant must treat the latest active files supplied or actually loaded as the source of truth and must not reconstruct them from memory.

------------------------------------------------------------------------

## 20. SOLO113 ADDITION — MAXIMUM CAPABILITY AND SYNCHRONIZATION CTX231 / OP113 / SCRIPT409

165. SOLO113 is the Operator version aligned with the final delivery:

```text
CTX231 / OP113 / SCRIPT409
```

166. The final delivery must include the following active public files:

```text
README.md
_CUSTOM_INSTRUCTIONS.md
_RULES_SOLO231_CONTEXTUALIZATION.md
_RULES_SOLO409_SCRIPTING.md
_RULES_SOLO113_RULESOPERATOR.md
_RULES_SOLOLAST_CONTEXTUALIZATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
```

167. `SOLOLAST` files must be exact binary or textual copies of the latest active versions of their respective families.

168. The public README must mention CTX231, SCRIPT409, and OP113 together with the current public structure.

169. Public presence of `AI_STUDYING_FILES/` is explicitly allowed when the user confirms it is intentional.

170. `_RULES_PRIVATE_*` remains allowed as a generic exclusion pattern.

171. Exact real private filenames remain prohibited in public files, public examples, README, public packages, and the GitHub remote.

172. The next Operator chat must start from complete files supplied or actually loaded, not from a reconstruction based on memory.

------------------------------------------------------------------------

## 21. SOLO OPERATOR RULE — MAXIMUM AVAILABLE MODEL AND REASONING

173. A SOLO Operator chat must use the most capable model actually available in the user’s interface and subscription.

174. The associated reasoning, intelligence, or effort level must be set to the maximum actually available.

175. At the start or activation of SOLO Operator mode, the assistant must briefly remind the user to select the most capable model and highest available reasoning level.

176. If the user has already explicitly said that the maximum model and level are active, the assistant must not repeat this reminder unnecessarily in the same chat.

177. Commercial model names and effort labels must not be hard-coded in this rule because they may change. The permanent reference is the maximum actually offered to the user at the time of the chat.

178. The assistant must never claim to have changed the model or reasoning level itself unless the interface explicitly gives it that capability.

179. If the assistant cannot verify the active model or level, it must say so clearly and ask only that the user check the interface selector.

180. The user may explicitly impose another model or a lower level for a specific operation. This explicit exception does not change the default rule for future SOLO Operator chats.

181. Core rule: unless the user explicitly chooses otherwise, every SOLO Operator chat must operate with the highest model capability and reasoning level actually available.

------------------------------------------------------------------------

## 22. SOLO114 ADDITION — LATEST VERSIONS KNOWN IN CHAT AND VERIFIED ON GITHUB

182. When the user asks for the latest SOLO versions, the assistant must provide separately:
- the latest versions mentioned, loaded, or validated in the current chat;
- the latest versions actually verified on the `main` branch of the `ai-context-rules` GitHub remote;
- a conclusion clearly stating whether the two sets are identical or different.

183. Versions known in the current chat must come from history actually available in the chat. They must not be presented as GitHub-verified versions.

184. Remote versions must be read from the headers of the three active public `SOLOLAST` files or the active versioned files actually present on GitHub `main`:

```text
_RULES_SOLOLAST_CONTEXTUALIZATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
```

185. The comparison concerns version numbers declared in the headers. A binary, byte-for-byte, or complete-content comparison is not necessary for a simple latest-version request.

186. If GitHub versions are newer than those known in the chat, the assistant must report the available update. It should fully load or apply the new rules only if the user’s request includes loading or applying them.

187. If chat and GitHub versions are identical, say so directly without launching an unnecessary content comparison.

188. If GitHub cannot be verified, provide versions known in the chat and explicitly state that remote versions were not verified. Never invent or present as remote a version known only from the chat.

189. Failure of a first access method is not enough to conclude GitHub is inaccessible. Depending on actual capabilities, the assistant must try:
- the public GitHub page;
- the public `raw.githubusercontent.com` URL;
- connected GitHub access or a GitHub connector;
- remote Git read or another authorized public method.

190. The assistant must identify exactly which method failed and continue with other available methods, without bypassing any security or authorization restriction.

191. When claiming to have read all SOLO rules, the assistant must actually have opened and read in full, during the current chat, the three `SOLOLAST` files for contextualization, scripting, and rules operator.

192. A file known only through memory, a summary, old context, or a version number does not count as fully read in the current chat.

193. After a generic request to read all SOLO rules, the assistant must confirm the three files and versions actually loaded separately.

194. Requests explicitly limited to one specialized family continue to load only the general contextualization family and then the requested specialized family.

195. For the SOLO114 delivery, expected active public versions are:

```text
CTX231 / OP114 / SCRIPT409
```

------------------------------------------------------------------------

## 23. SOLO115 ADDITION — 5000-CHARACTER CUSTOM INSTRUCTIONS LIMIT

196. The public `_CUSTOM_INSTRUCTIONS.md` intended for the Custom Instructions field must contain at most 5000 characters.

197. The limit includes every character actually present, including letters, digits, punctuation, spaces, tabs, and line breaks.

198. Before any delivery containing `_CUSTOM_INSTRUCTIONS.md`, the assistant must measure its actual length using a reliable method and report the result.

199. A delivery whose `_CUSTOM_INSTRUCTIONS.md` exceeds 5000 characters is invalid and must never be presented as complete or compliant.

200. If the limit is exceeded, compact the file first by removing repetitions, redundant examples, unnecessary spaces, long wording, and decorative sections.

201. Compaction must not remove, weaken, or alter any approved functional behavior, including:
- SOLO startup bypass;
- default CTX loading;
- loading all three families on explicit full-read request, especially `read all SOLO rules`;
- contextual reapplication without adding an out-of-scope family;
- specialized routing by family;
- authorized GitHub fallback chain;
- prohibition on false read claims;
- separate confirmation of files and versions actually loaded.

202. Markdown readability may be reasonably reduced to satisfy the limit, but triggers, priorities, URLs, conditions, and expected results must remain unambiguous.

203. Character count must be checked on the exact final file after all modifications and before creating ZIPs.

204. The file contained in every ZIP must be strictly identical to the measured final file.

205. README, Operator changelog, and delivery documentation must mention this limit when an Operator version introduces or changes it.

206. For SOLO115 delivery, expected active public versions are:

```text
CTX231 / OP115 / SCRIPT409
```

------------------------------------------------------------------------

## 24. SOLO116 ADDITION — REPOSITORY GUARANTEES ALIGNED WITH SCRIPT410

207. When an Operator request provides repository evidence such as an `ll -R` or `tree` listing, creation or Git logs, `.git/`, `.gitignore`, a repository URL, archive, or project files, `scripting repo` mode must be activated automatically even without explicit wording.

208. During all SOLO maintenance or delivery, `AGENTS.md` must never be modified.

209. The `CLAUDE.md -> AGENTS.md` link must never be deleted, replaced, recreated, transformed, or automatically repaired.

210. Before and after each delivery, the assistant must verify that `CLAUDE.md` remains a symbolic link pointing exactly to `AGENTS.md` and that the `AGENTS.md` fingerprint is unchanged.

211. Any delivery containing `.gitignore` must preserve all existing entries and additively merge the mandatory baseline defined by SCRIPT410, without deletion.

212. If the existing `.gitignore` is neither supplied nor accessible, the assistant must request it before final delivery. It must never replace it with only the minimal baseline.

213. The mandatory baseline is:

```gitignore
.old/
.docs/
.tmp/
.log/
.logs/
.zip/
.tracking_data/
.report/
.reports/
.webactivity_reports/
.exported_activity/
.result/
.results/
logs/
output/
.output/
infos/
.info/
uploads/
creation_log/
certs/
secrets/
.secrets/
.private/
*RULES_PRIVATE*
```

214. Strictly identical duplicates may be removed, but no differently scoped variant or existing exclusion may be deleted.

215. Before creating ZIPs, automatically verify the presence of every mandatory entry in the final `.gitignore`.

216. For SOLO116 delivery, expected active public versions are:

```text
CTX231 / OP116 / SCRIPT410
```

------------------------------------------------------------------------

## 25. SOLO117 ADDITION — GLOBAL SYNCHRONIZATION CTX232 / OP117 / SCRIPT410

217. SOLO117 validates that SCRIPT410 repository guarantees are also integrated into general contextualization CTX232 and apply regardless of the active mode.

218. Custom Instructions must trigger SOLO Scripting loading when repository evidence is provided, including a tree, `ll -R` or `tree` output, Git or creation logs, repository URL, archive, or structural project files.

219. The final length of modified Custom Instructions must remain at or below 5000 characters and must be measured before packaging.

220. CTX232, SCRIPT410, and OP117 must contain compatible requirements regarding automatic repo-mode activation, `AGENTS.md` immutability, preservation of `CLAUDE.md -> AGENTS.md`, and additive `.gitignore` merging.

221. Before delivery, verify that CTX232 and OP117 have exact `SOLOLAST` aliases and that SCRIPT410 remains identical to its active alias.

222. The delivery must never include a copy intended to replace `AGENTS.md` or `CLAUDE.md`.

223. For SOLO117 delivery, expected active public versions are:

```text
CTX232 / OP117 / SCRIPT410
```

------------------------------------------------------------------------

## 26. SOLO118 ADDITION — ANTI-DUPLICATE AND ANTI-OVERLAP CHECK

224. As soon as the user supplies, proposes, or asks to integrate a new rule, the assistant must search for relevant existing rules before any integration.

225. The search must cover the relevant SOLO families - CTX, SCRIPT, and OP - as well as reference files actually supplied or loaded in the current chat. The assistant must not present a rule known only from memory as verified.

226. The comparison must examine meaning, scope, triggers, obligations, exceptions, priorities, and expected results, not merely identical wording.

227. Classify the result as: rule absent, exact duplicate, partial overlap, complementary rule, conflict, or existing rule too vague.

228. If the new rule is already covered fully or partially, do not create a parallel rule. Propose a merge, clarification, or targeted sub-rule while preserving the most protective existing behavior.

229. Before any modification, briefly state: the relevant existing rule, the part already covered, the genuinely new part, and the minimal proposed action.

230. After integration, verify there is no duplicate, contradiction, weakening, unnecessary repetition, or obsolete reference, then check numbering and version.

231. This verification is mandatory even if the user presents the rule as new, urgent, corrected, or already validated in another chat.

------------------------------------------------------------------------

## 27. SOLO118 ADDITION — READ ALOUD BEHAVIOR AND CTX233 SYNCHRONIZATION

232. The canonical command is `switch to Read Aloud mode`. It activates a chat-presentation mode; it does not request a separate action called `reread in Read Aloud`.

233. When switching from inactive to active in a chat that already contains a useful answer, the assistant must immediately re-emit that latest answer in a form suitable for listening and must not reply only with a confirmation.

234. The re-emission must preserve the substance, nuances, conditions, decisions, steps, and conclusion of the normal answer. Read Aloud mode does not impose any automatic length reduction.

235. Sentences, paragraphs, headings, and lists may be adapted for listening. Dense tables may be converted to prose or lists, but no useful information may be removed.

236. An explicit request such as `short version`, `summary`, `shorter`, or equivalent is required to reduce content. Re-activating the mode while it is already active must not automatically retrigger re-emission and create a loop.

237. OP118 must remain compatible with CTX233, and this section must not be interpreted as a separate or competing rule for the global Read Aloud mode.

------------------------------------------------------------------------

## 28. SOLO118 ADDITION — SYNCHRONIZATION AND ACTIVE VERSION

238. SOLO118 is aligned with the following public delivery:

```text
CTX233 / OP118 / SCRIPT410
```

239. `SOLOLAST` files must be exact copies of the latest active CTX, OP, and SCRIPT versions.

240. Before delivery, verify CTX232 inheritance in CTX233 and OP117 inheritance in OP118, absence of modification to SCRIPT410, alias consistency, package validity, and absence of private names in public files.

241. The delivery must never replace, modify, recreate, or automatically repair `AGENTS.md` or the `CLAUDE.md -> AGENTS.md` link.

------------------------------------------------------------------------

## 29. SOLO119 ADDITION — CONTEXTUAL REAPPLICATION OF CUSTOM INSTRUCTIONS AND SOLO FAMILIES

242. SOLO119 integrates the global behavior defined by CTX234 to refresh the rules of an already-open chat after a public-repository update.

243. Phrases such as `reload the rules`, `reapply the rules`, `reload the SOLO rules`, `reapply the SOLO rules`, `reload the Custom Instructions`, `reapply the Custom Instructions`, `apply the latest rules`, `I updated the rules on GitHub`, or equivalent first trigger an actual read of the current public `_CUSTOM_INSTRUCTIONS.md`.

244. This read constitutes functional reapplication to the current chat. The assistant must not claim to have technically reloaded, modified, or synchronized the ChatGPT account setting itself.

245. After rereading Custom Instructions, CTX must always be reread from `_RULES_SOLOLAST_CONTEXTUALIZATION.md`.

246. Scripting must be reread only if the current chat already concerns scripting, code, a durable script, Git repository, extension, application, development, debugging, or code-related technical documentation.

247. Operator must be reread only if the current chat already concerns Operator mode or SOLO-rule maintenance, correction, creation, versioning, merging, packaging, or delivery.

248. If both Scripting and Operator scopes are already active in the current chat, reread all three families.

249. A simple reapplication request must never add an unrelated family to the current context merely because it contains the words `SOLO rules`, `the rules`, or `all`.

250. The explicit command `read all SOLO rules`, or a request explicitly framed as reading/loading all three families, remains distinct and forces full reading of CTX, then Scripting, then Operator.

251. A request explicitly limited to one specialized family reloads CTX and then only that family.

252. If the new request genuinely changes chat scope - for example explicit Operator activation, starting coding work, or providing repository evidence - normal family activation rules continue to apply.

253. Startup bypass does not block a later requested reapplication in the chat. The explicit request authorizes reads corresponding to the current scope.

254. After reapplication, briefly confirm the actual read of public Custom Instructions, the SOLO families reread, their versions, and the old/new version when the old one is known. Any read failure must be identified without false confirmation.

255. `_CUSTOM_INSTRUCTIONS.md` must remain at or below 5000 characters after integrating this behavior, and its exact count must be checked on the final file.

256. For SOLO119 delivery, expected active public versions are:

```text
CTX234 / OP119 / SCRIPT410
```

257. CTX234 and OP119 `SOLOLAST` aliases must be exact copies of the corresponding versioned files. SCRIPT410 and its alias must remain strictly unchanged.

258. Before delivery, verify there is no contradiction with explicit three-family reading, specialized routing, startup bypass, automatic repo-mode activation, and immutable `AGENTS.md` / `CLAUDE.md` guarantees.

259. Core rule: reapplication refreshes families already relevant to the chat; it does not turn a normal chat into a Scripting or Operator chat without a genuine scope change.

------------------------------------------------------------------------

## 30. SOLO120 ADDITION — MANDATORY POST-PUSH VALIDATION AND TEST PROMPT

260. A delivery of new SOLO RULES intended for the public repository does not end with the ZIP. In the same delivery, the Operator must prepare the post-push check that verifies the versions actually published are the expected ones and that bootstrap/routing works.

261. The post-push check complements already-required packaging, `SOLOLAST` alias, non-regression, size, documentation, and consistency checks. It does not replace them.

262. For every new CTX, Scripting, or Operator version intended for GitHub, the delivery response must also provide:
- the final ZIP package;
- identification of the expected new versions;
- a post-push prompt or prompt sequence ready to paste into a new chat;
- expected results for each test step.

263. The user remains responsible for updating the local repository and performing `git push`. When the user uses `gita`, that term may refer to a local commit/push alias; the Operator must not claim to have run it without actual environment/action access.

264. The test prompt must be generated BEFORE the delivery ends, without waiting for the user to return and ask how to test. It must match the exact current-release versions.

265. If several public families are affected, the test must at minimum separately verify:
1. new-chat bootstrap: CTX only;
2. Scripting activation on clear repository evidence;
3. explicit Operator activation;
4. reread/reload of already-active families without unwanted additions.

266. For a change limited to one family, the Operator may reduce the test to necessary steps, but must still test the bootstrap or routing that actually reaches the new version.

267. The test must instruct the new chat to report only files actually read and return their exact versions. A response based only on memory, previous context, or assumption is insufficient.

268. Expected output must use exact active versions from the current delivery. Generic example:

```text
CTX<version> / SCRIPT<version> / OP<version>
```

The Operator must never mechanically reuse version numbers from a previous delivery.

269. When the test is sequential, each test message must be provided in exact execution order and state that it is to be sent in the same chat after initial bootstrap, except for the first message, which must be sent in a new chat.

270. Post-push validation is successful only when observed results match expected versions and families. If a remote version is old, an alias is wrong, a family is missing, or an unwanted family appears, the Operator must classify the test as failed and investigate the cause before treating delivery as final.

271. If the GitHub repository has not yet been pushed, the prompt is still provided immediately with the ZIP, but must be labeled `POST-PUSH TEST - RUN AFTER GITA/PUSH`.

272. After push confirmation, if the user returns test responses or screenshots, the Operator must compare them with expected results and answer clearly `VALIDATED` or `FAILED`, with the exact discrepancy on failure.

273. The test file may be included in the ZIP under a clear name such as `POST_PUSH_TEST_PROMPT.md`, but its presence does not exempt the Operator from also providing the prompt directly in the delivery response when useful for immediate execution.

274. Core rule: **every new RULES delivery intended for GitHub must ship with its final ZIP AND a ready-to-run post-push test; the user must not have to return and ask how to verify publication.**

------------------------------------------------------------------------

## 31. SOLO121 ADDITION — POST-PUSH TEST GENERATED IN CHAT, NO PROMPT FILE

275. SOLO121 corrects and clarifies the post-push mechanism introduced by SOLO120.

276. The post-push test must NOT be delivered as a persistent file such as `POST_PUSH_TEST_PROMPT.md`, nor added to repository root, `.docs/`, or `.zip/` as a normal work artifact.

277. The test prompt is conversational content generated by the Operator at the appropriate time. It belongs in the chat response, not the repository.

278. Mandatory workflow:
1. the Operator creates/modifies the RULES and delivers the final ZIP;
2. the user places the files in the local repository and performs commit/push, for example using local alias `gita` if desired;
3. the user confirms in chat that the push is complete (`pushed`, `gita done`, `uploaded`, `it is online`, or equivalent);
4. immediately after that confirmation, the Operator displays in its response the exact prompt(s) to paste into a new chat;
5. prompts are adapted to the exact versions just published;
6. the user returns the result or a screenshot;
7. the Operator states clearly `VALIDATED` or `FAILED` and gives the exact discrepancy if needed.

279. Before push confirmation, the Operator may remind the user that a post-push test will be required, but must not create a prompt file or clutter the package with that content.

280. When multiple test steps are necessary, display them directly in the conversation as ready-to-paste blocks in execution order: new chat first, then subsequent messages in the same chat if required.

281. The RULES package must remain a package of RULES and necessary documentation. The post-push prompt is not a repository file.

282. The previous versioned RULE must leave repository root when a new version becomes active and must be archived under `.old/`. An already-versioned file, for example `_RULES_SOLO120_RULESOPERATOR.md`, may keep its name under `.old/` because it is inherently unique.

283. `SOLOLAST` aliases are never archived as old versions: replace them with the exact copy of the new active version.

284. If an archived file could overwrite an existing file under `.old/`, give it a unique name before archiving, containing at minimum its version or, for non-versioned files, an explicit archive date/version.

285. Core rule: **after a confirmed push, the Operator displays the post-push test directly in chat; no `POST_PUSH_TEST_PROMPT.md` file may be created or delivered.**

------------------------------------------------------------------------

## 32. SOLO122 ADDITION — COMMIT-PINNED POST-PUSH CHAIN TEST

286. SOLO122 extends SOLO121. The reference post-push test must now be a **single CHAIN TEST**, executable with one copy/paste in a new chat.

287. The final post-push acceptance test must never use floating branch `main` as the source of truth for RULES being validated. RAW URLs used by the test must be pinned to the exact SHA of the commit just pushed.

288. After push confirmation (`gita done`, `pushed`, `uploaded`, `it is online`, or equivalent), the Operator must:
1. identify the SHA of the commit actually pushed from Git output supplied in chat or from an actual remote read if available;
2. when possible, verify that the commit is accessible on the remote;
3. build RAW URLs with that SHA;
4. immediately display in chat one `POST-PUSH SOLO CHAIN TEST - COMMIT PINNED` prompt ready to paste into a new chat.

289. If no reliable SHA is available, the Operator must not invent a commit or silently fall back to `main`. It must request or retrieve the real SHA before producing the final acceptance test.

290. Canonical test-source format:

```text
COMMIT=<sha>
CTX_RAW=https://raw.githubusercontent.com/<owner>/<repo>/<sha>/_RULES_SOLOLAST_CONTEXTUALIZATION.md
SCRIPT_RAW=https://raw.githubusercontent.com/<owner>/<repo>/<sha>/_RULES_SOLOLAST_SCRIPTING.md
OP_RAW=https://raw.githubusercontent.com/<owner>/<repo>/<sha>/_RULES_SOLOLAST_RULESOPERATOR.md
```

291. The complete CHAIN TEST must automatically execute these steps in one response, without requesting `NEXT`:
1. BOOTSTRAP: actually read `CTX_RAW` only;
2. REPOSITORY: actually read `SCRIPT_RAW`;
3. OPERATOR: actually read `OP_RAW`;
4. RELOAD: actually reread `CTX_RAW`, `SCRIPT_RAW`, and `OP_RAW`.

292. A step is `PASS` only if the required file(s) were actually opened and read from commit-pinned URLs. A version inferred from memory, context, another RULE, an old chat, a local alias, or a previous step never counts as validation.

293. The prompt must explicitly contain:

```text
ABSOLUTE RULE:
a step is PASS only if the required file is actually opened and read from the pinned URL above.
Never infer a version from memory, context, or another RULE.
If a required remote read fails: FAIL.
```

294. Expected versions must be calculated from the current delivery, never copied from an old test. Example:

```text
STEP 1: CTX<version>
STEP 2: CTX<version> + SCRIPT<version>
STEP 3: CTX<version> + SCRIPT<version> + OP<version>
STEP 4: CTX<version> + SCRIPT<version> + OP<version>
```

295. Expected test-chat response must remain compact:

```text
STEP 1: PASS/FAIL - observed versions
STEP 2: PASS/FAIL - observed versions
STEP 3: PASS/FAIL - observed versions
STEP 4: PASS/FAIL - observed versions
FINAL VERDICT: VALIDATED or FAILED
First divergence: <cause>, only on failure.
```

296. If only some families are modified, the Operator may adapt expected versions, but the full CTX -> Scripting -> Operator -> Reload test remains the reference test when an Operator or bootstrap/routing change is delivered.

297. The post-push test remains chat content. No `POST_PUSH_TEST_PROMPT.md` file may be created, delivered, or added to the repository.

298. After receiving CHAIN TEST results, the Operator must answer clearly:
- `POST-PUSH SOLO CHAIN TEST: VALIDATED` if all steps PASS;
- `POST-PUSH SOLO CHAIN TEST: FAILED` otherwise, with the first divergence.

299. A failure caused by an old version read through floating `main` must not lead directly to RULE changes. The Operator must first repeat or correct the test using the commit SHA actually pushed.

300. Core rule: **every Operator or bootstrap delivery intended for GitHub must, after confirmed push, automatically produce one CHAIN TEST pinned to the exact commit SHA; no final acceptance test may depend on `main`.**

------------------------------------------------------------------------

## 33. SOLO123 ADDITION — OPERATOR FULL ACCEPTANCE TEST

301. SOLO123 fully preserves the SOLO122 CORE POST-PUSH CHAIN TEST and adds a second validation level: the **FULL ACCEPTANCE TEST**.

302. The CORE CHAIN TEST remains mandatory after every relevant push. It validates minimum routing:
1. CTX;
2. Scripting;
3. Operator;
4. Reload;
with actual reads pinned to the exact commit SHA.

303. FULL ACCEPTANCE is mandatory after any modification that affects at least one of these areas:
- RULESOPERATOR;
- Custom Instructions bootstrap;
- SOLO-family routing;
- reload/reapplication logic;
- delivery or packaging rules;
- old-version management;
- `SOLOLAST` aliases;
- post-push validation;
- anti-overlap/anti-duplication rules;
- expected public repository structure.

304. FULL ACCEPTANCE never replaces CORE CHAIN. Mandatory workflow:
1. confirmed push;
2. remote-commit verification when possible;
3. commit-pinned CORE CHAIN TEST;
4. if CORE = VALIDATED, FULL ACCEPTANCE TEST;
5. final release-validation verdict.

305. FULL ACCEPTANCE must be generated directly in chat. No persistent test-prompt file may be created.

306. The behavioral part of FULL ACCEPTANCE must be executable with **one copy/paste** in a new chat.

307. FULL ACCEPTANCE must distinguish two categories:
A. real repository checks, performed by the Operator when it has actual repository access;
B. behavioral checks performed in a new chat with actual reads of commit-pinned RULES.

308. Real repository checks to perform when technically available:
- announced commit SHA exists on remote;
- `SOLOLAST` files point to expected versions;
- active numbered version exists;
- previous numbered version does not remain at root when it should be archived;
- previous version is present under local `.old/` if observable;
- no `POST_PUSH_TEST_PROMPT.md` is published;
- `.gitignore` was not modified without justification;
- `AGENTS.md` was not modified;
- `CLAUDE.md` was not replaced, recreated, or modified;
- public README references correct active versions;
- prohibited private or local files are not published;
- commit contains no obvious naming regression.

309. If a real repository check is not technically observable from the Operator environment, mark it `NON OBSERVABLE`, not `PASS`.

310. Behavioral FULL ACCEPTANCE must test at minimum:
1. CTX-only bootstrap;
2. Scripting activation on clear repository evidence;
3. Operator activation on explicit request;
4. reload without unwanted family activation;
5. actual file reads from SHA-pinned URLs;
6. refusal to infer a version from memory/context;
7. anti-overlap: search for an existing rule before creating a new one;
8. problem classification: absent / duplicate / partial overlap / complementary / conflict / too vague;
9. if a rule already exists, do not create a parallel rule;
10. single-file delivery: direct file;
11. multi-file delivery: from two files onward, one mandatory ZIP;
12. previous numbered version: must not remain active at root;
13. `SOLOLAST`: must exactly match active version;
14. no `POST_PUSH_TEST_PROMPT.md` file;
15. post-push test provided in chat;
16. post-push test pinned to commit SHA, never `main`;
17. compact, deterministic final verdict.

311. Behavioral tests that simulate a dangerous or destructive operation must not actually modify the repository. They must ask the chat to describe the compliant expected decision.

312. Packaging tests must use synthetic scenarios:
- scenario A: one final output -> expected: direct delivery;
- scenario B: two final outputs -> expected: one ZIP containing both final files;
- scenario C: a file inside the ZIP changes after creation -> expected: mandatory ZIP recreation.

313. For anti-overlap, provide a scenario in which a rule already partially covers the request and verify that the Operator:
- searches for the existing rule;
- identifies what is already covered;
- identifies what is genuinely new;
- chooses the minimal modification;
- does not create an unnecessary parallel rule.

314. For archival checks, verify this decision:
- new active version at root;
- previous numbered version archived under `.old/`;
- `SOLOLAST` replaced by exact copy of the new active version;
- no historical alias archived as a numbered version.

315. For repository protection, verify that the Operator refuses to:
- modify or recreate `AGENTS.md`;
- modify or recreate `CLAUDE.md`;
- clean up or rewrite `.gitignore` without validated need;
- publish `.docs/`, `.old/`, `.private/`, ZIPs, or `_RULES_PRIVATE_*` at public root when they are meant to remain local/ignored.

316. FULL ACCEPTANCE must show a result for each check in this form:

```text
CHECK <n>: PASS / FAIL / NON OBSERVABLE - <short summary>
```

317. Final verdict must be:

```text
FULL ACCEPTANCE: VALIDATED
```

only if all mandatory observable checks PASS and no mandatory check FAILS.

318. If one or more checks are `NON OBSERVABLE`, the Operator may conclude:

```text
FULL ACCEPTANCE: VALIDATED WITH NON-OBSERVABLE CHECKS
```

only if no observable check fails, and must list the exact non-observable checks.

319. On failure, identify the exact first divergence and do not immediately propose a new RULE before determining whether failure comes from:
- a missing rule;
- a rule that is too vague;
- an existing rule not applied;
- a misinterpretation;
- an incorrect test;
- cache or an unpinned floating source.

320. A failure of the test itself must never automatically be interpreted as a defect in the RULES.

321. Before any new modification after a failure, apply the existing anti-overlap check and determine whether an existing rule already covers the expected behavior.

322. After a validated CORE CHAIN TEST, if the change falls within rule 303, automatically propose FULL ACCEPTANCE without waiting for the user to ask.

323. If the user explicitly asks `test everything`, `make it bulletproof`, `test as much as possible`, `full test`, `full acceptance`, or equivalent, run/propose FULL ACCEPTANCE even when the current change does not strictly fall under rule 303.

324. FULL ACCEPTANCE must be dynamically adapted to exact versions of the current release. Never mechanically copy version numbers from an old test.

325. FULL ACCEPTANCE must be pinned to the same SHA as the release CORE CHAIN TEST.

326. If a new commit is pushed between CORE and FULL, FULL must use the new SHA and CORE must be considered to belong to the old commit.

327. Release verdict must always state both levels:

```text
CORE CHAIN: VALIDATED / FAILED
FULL ACCEPTANCE: VALIDATED / VALIDATED WITH NON-OBSERVABLE CHECKS / FAILED
```

328. An Operator/bootstrap/routing/delivery release is fully validated only after:
- CORE CHAIN validated;
- FULL ACCEPTANCE validated, or validated with explicitly listed non-observable checks.

329. Core rule: **for every Operator, bootstrap, routing, or delivery change, the standard post-push check is CORE CHAIN + FULL ACCEPTANCE, both pinned to the exact commit SHA; FULL must test as many behaviors and invariants as technically possible without actually modifying the repository.**

------------------------------------------------------------------------

## 34. SOLO124 ADDITION — CANONICAL 20-CHECK FULL ACCEPTANCE TEMPLATE

330. SOLO124 does not create a parallel mechanism. It **clarifies and standardizes** the FULL ACCEPTANCE already required by SOLO123.

331. After CORE CHAIN validation, when FULL ACCEPTANCE is required by rules 303, 322, or 323, the Operator must **automatically** generate one canonical behavioral FULL ACCEPTANCE as a single copy/paste block.

332. Canonical FULL ACCEPTANCE must be pinned to the same exact SHA as CORE CHAIN unless a new commit was pushed in the meantime, in which case rules 325 and 326 apply.

333. Canonical FULL ACCEPTANCE contains **20 mandatory behavioral checks**, grouped in this order:

### A — ROUTING / LOADING
1. CTX-only bootstrap.
2. Scripting activation on repository evidence.
3. Explicit Operator activation.
4. Reload without unrelated family activation.
5. Confirmation of actual reads from pinned URLs.
6. Anti-memory: the pinned RAW source wins over memory/old context.

### B — RULE ANTI-OVERLAP
7. Search for an existing rule before creating a new one.
8. Handle partial overlap through minimal delta/merge.
9. Canonical classification: absent / exact duplicate / partial overlap / complementary / conflict / existing rule too vague.

### C — DELIVERY / PACKAGING
10. One final file -> direct delivery.
11. Two or more final files -> one mandatory ZIP.
12. File inside ZIP modified after creation -> mandatory ZIP recreation.

### D — VERSIONING / ARCHIVING
13. New active version at root; previous numbered version removed from root and archived under `.old/`.
14. `SOLOLAST` replaced by exact active-version copy; old `SOLOLAST` not archived as a historical version.

### E — REPOSITORY PROTECTION
15. Protect `AGENTS.md`, `CLAUDE.md`, and preserve `.gitignore`.
16. Do not publish `.docs/`, `.old/`, `.private/`, `*.zip`, or `_RULES_PRIVATE_*` when these are local/ignored.

### F — POST-PUSH
17. No `POST_PUSH_TEST_PROMPT.md`; prompt generated directly in chat.
18. Final test pinned to exact commit SHA; never `main`.
19. One CHAIN TEST ready to paste; no `NEXT`.
20. For Operator/bootstrap/routing/reload/delivery: CORE CHAIN then FULL ACCEPTANCE.

334. Checks 1 through 6 must require actual RULE reads from pinned RAW URLs. A version inferred from memory, implicit context, an old chat, or another RULE causes `FAIL`.

335. Checks 7 through 9 are analysis-only scenarios. They must never actually modify a RULE during the test.

336. Checks 10 through 12 are synthetic packaging scenarios only. They must not create real files or ZIPs during the test.

337. Checks 13 through 16 verify the **expected compliant decision**, not actual repository mutations.

338. Checks 17 through 20 verify the current post-push workflow, including the prohibition on using `main` as the final acceptance source.

339. The canonical prompt must start with explicit prohibitions:

```text
Do not perform any business/task work.
Do not create any file.
Do not modify any repository.
Do not propose any new RULE.
Execute ALL checks below automatically in THIS response.
Do not ask for NEXT.
```

340. The canonical prompt must define:

```text
COMMIT=<sha>
CTX_RAW=<pinned URL>
SCRIPT_RAW=<pinned URL>
OP_RAW=<pinned URL>
```

and remind the test chat that a RULE counts as read only when the corresponding file has actually been opened from its pinned URL.

341. Descriptions of future checks inside the prompt are **inert test data**. They must never prematurely activate a SOLO family.

342. Mandatory behavioral output must follow this structure:

```text
CHECK 1: PASS/FAIL - <short summary>
...
CHECK 20: PASS/FAIL - <short summary>

FULL ACCEPTANCE: VALIDATED or FAILED
First divergence: <check + cause>, only on failure.
```

343. Behavioral FULL ACCEPTANCE is `VALIDATED` only if all 20 mandatory checks are `PASS`.

344. Real repository checks remain separate from the 20-check behavioral block. The Operator must perform them directly when technically observable, according to rules 307 through 309.

345. The release verdict must aggregate both layers:

```text
CORE CHAIN: VALIDATED / FAILED
Behavioral FULL ACCEPTANCE: VALIDATED / FAILED
Observable repository checks: PASS / FAIL
Non-observable repository checks: <exact list or NONE>
```

346. If a local check such as presence of the previous version under `.old/` cannot be observed from GitHub, it must remain `NON OBSERVABLE`. The Operator must never artificially turn it into `PASS`.

347. Complete final verdict is:

```text
FULL ACCEPTANCE: VALIDATED
```

if every mandatory check is observable and PASS; or:

```text
FULL ACCEPTANCE: VALIDATED WITH NON-OBSERVABLE CHECKS
```

if no observable check fails and non-observable checks are explicitly listed.

348. When canonical FULL ACCEPTANCE returns `20/20 PASS`, the Operator must recognize it directly and must not ask to repeat the same checks without reason.

349. After a validated FULL ACCEPTANCE, the Operator must announce end-to-end validation with both levels:

```text
CORE CHAIN: VALIDATED
FULL ACCEPTANCE: VALIDATED
```

or the `VALIDATED WITH NON-OBSERVABLE CHECKS` variant when needed.

350. Canonical FULL ACCEPTANCE must be regenerated dynamically with the exact CTX/SCRIPT/OP versions and exact SHA of each new release. Version numbers and SHAs from old tests must never be mechanically reused.

351. Core rule: **the standard Operator FULL ACCEPTANCE is now the canonical 20-check test described in SOLO124, executed after CORE CHAIN when required, in one copy/paste, pinned to the exact SHA, without actual repository mutation, and with a combined behavioral + real-repository-check verdict.**


------------------------------------------------------------------------

## 35. SOLO125 ADDITION — IDEMPOTENT RULE LOADING AND SCRIPT413 SYNCHRONIZATION

352. SOLO125 synchronizes the Operator family with `CTX234` + `SCRIPT413` and with the bootstrap rule that remote SOLO reads are idempotent inside an already-open chat.

353. Loading a public SOLO family is a state transition, not a per-message ritual. The chat must remember which public families were actually read and the versions observed.

354. Once CTX is loaded in the current chat, later activation of Scripting or Operator must read only the missing family unless an explicit reload/refresh is requested.

355. Once Scripting is active, the following do **not** trigger another CTX/SCRIPT remote read by themselves:
- the word `scripting`;
- continued code/debug work;
- repeated repository evidence;
- a question about a scripting rule;
- a complaint that a scripting rule was not followed;
- a request to correct code under the already-loaded scripting rules.

356. Once Operator is active, ordinary references to Operator/rules maintenance likewise do not trigger another remote read.

357. A reread is required only when at least one of these is true:
- explicit `reload`, `reapply`, `refresh`, `load latest`, `load current rules`, or equivalent;
- the user states that the rules or repository were updated/pushed;
- the chat has no reliable evidence that the required family was actually read;
- a validation test explicitly requires a real pinned reread.

358. The anti-false-read rule remains absolute: cached loaded state can prevent unnecessary rereads, but the assistant must never claim that a family was read if no real read occurred earlier in the current chat.

359. After a rule family is loaded, rule violations must be corrected by applying the loaded content. Repeatedly rereading the same rule without correcting a known violation is not compliant behavior.

360. For Scripting releases, Operator validation must treat the canonical CLI compliance gate from SCRIPT413 as a blocking invariant where durable CLI scripts are in scope.

361. FULL ACCEPTANCE routing checks must additionally verify idempotence:
- first activation performs the required real read;
- a normal follow-up mentioning the already-active family does not reread it;
- explicit reload still performs a real reread.

362. The canonical 20-check FULL ACCEPTANCE remains 20 checks. The idempotence assertion is incorporated into routing/loading checks rather than creating a parallel 21st check.

363. When generating expected versions for CORE CHAIN or FULL ACCEPTANCE after this release, use the actual active versions dynamically. For this release baseline they are:
```text
CTX234
SCRIPT413
OP125
```
These values must still be replaced dynamically in future releases.

364. Core rule: **load each required SOLO family once per chat activation state, apply it continuously, reread only on explicit refresh/update/validation triggers, and never substitute repeated remote reads for actual compliance.**
