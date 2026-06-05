# Study Weaver

A customizable Claude Code skill for university-course learning and exam review.

Turns scattered course materials — slides, textbooks, homework, past papers, handwritten notes, and mistake records — into structured, readable, long-term study artifacts.

## Features

- **4 learning modes**: semester-sync, deep-review, exam-consolidation, survival-cram
- **Multi-format output**: Markdown (default), HTML, PDF, Anki CSV, Mermaid diagrams
- **Handwritten note workflow**: OCR extraction with uncertainty marking
- **Past-paper reverse engineering**: question-trigger chains, not just solutions
- **Mistake-driven review**: classify errors and generate mutation drills
- **Personalization**: `study_profile.md` adapts to your learning style

## Installation

Copy the `study-weaver/` folder into your Claude Code skills directory:

```bash
# macOS / Linux
cp -r study-weaver ~/.claude/skills/

# Windows (PowerShell)
Copy-Item -Recurse study-weaver $env:USERPROFILE\.claude\skills\
```

Restart Claude Code. The skill activates automatically when your prompt matches the triggers.

## Usage

Just describe your study situation in natural language:

```
帮我整理高频电子线路第2章，要知识地图和公式体系，冲90分
```

```
明天考通信原理，基本没学，帮我速通
```

```
I want to review Chapter 4 oscillators in English with Mermaid diagrams
```

## Learning Modes

| Mode | When | Goal |
|------|------|------|
| **Semester-sync** | Throughout the semester | Prevent knowledge gaps |
| **Deep-review** | Enough time, aiming 85+/90+ | Connected knowledge system |
| **Exam-consolidation** | Approaching exam, studied once | Convert notes to exam-ready |
| **Survival-cram** | Short on time, pass/75+ | Maximize score per hour |

## Personalization

Create a `study_profile.md` in your project root:

```markdown
# Study Profile

## Language Mode
中文解释 + 英文术语括注

## Goal
冲 85+/90+，重视理解、题型迁移和错题回收。

## Learning Style
- 先看知识地图
- 再看公式体系
- 然后看题型调用链
- 最后做自测和错题回收

## Output Preference
- 默认生成 Markdown
- HTML 只在要求阅读版时生成
- Anki CSV 用于公式和易错判断

## Course Type
STEM calculation-heavy
```

See the full template in [SKILL.md](SKILL.md).

## File Structure

```
study-weaver/
├── SKILL.md          # Main skill definition
├── evals/
│   └── evals.json    # Evaluation test cases
└── README.md         # This file
```

## Customization

This skill is designed to be forked and adapted:

1. Edit `SKILL.md` description if you want narrower/broader triggers
2. Add learner preferences to `study_profile.md`, not hardcoded in the skill
3. Add course-specific examples only when they teach a general pattern
4. Keep formulas in LaTeX and knowledge maps visual

## License

MIT
