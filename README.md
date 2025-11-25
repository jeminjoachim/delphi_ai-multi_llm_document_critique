# delphi_ai-multi_llm_document_critique
A Delphi technique-inspired AI system that uses multiple Large Language Models to provide comprehensive, iterative critiques of documents. Think of it as having a panel of expert reviewers analyze your work through multiple rounds of refinement.

## What Makes This Special?

Traditional document review relies on individual perspectives. This system:
- **Leverages Multiple AI Models** - Uses Llama 3.3, DeepSeek, and Qwen for diverse analytical perspectives
- **Implements Delphi Methodology** - Two-round iterative critique process where models refine their analysis after seeing others' insights
- **Synthesizes Intelligently** - GPT-OSS combines all perspectives into one comprehensive final critique
- **Identifies Consensus & Contradictions** - Shows what all models agreed on and where perspectives differ

## How It Works

```
Document Input
    ↓
┌─────────────────────────────────────┐
│  ROUND 1: Independent Analysis      │
│  - Llama 3.3 critiques              │
│  - DeepSeek critiques               │
│  - Qwen critiques                   │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│  ROUND 2: Refined Analysis          │
│  Each model sees others' critiques  │
│  and refines their own assessment   │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│  SYNTHESIS: GPT-OSS Integration     │
│  Combines all insights into         │
│  comprehensive final critique       │
└─────────────────────────────────────┘
    ↓
Final Report (TXT/DOCX/PDF)
```

## 🚀 Quick Start

### Prerequisites

```bash
pip install cerebras-cloud-sdk PyPDF2 python-docx reportlab requests
```

### API Keys Required

- **Cerebras API Key** (free tier available) - for Llama, Qwen, and GPT-OSS
- **DeepSeek API Key** (free tier available)

### Basic Usage

```python
from delphi_critique import delphi_critique_system, save_results

# Run the critique
result = delphi_critique_system(
    document_path="your_document.pdf",
    task_instruction="Critically evaluate this document and identify areas for improvement."
)

# Save results
save_results(result, "output", format="docx")  # or "txt" or "pdf"
```

## Demo: Critiquing "The Intelligence Age" by Sam Altman

This repository includes a real-world demo analyzing Sam Altman's September 2024 essay on AI's future impact. The system:

- **Round 1**: Each model independently analyzed the essay's predictions, assumptions, and logic
- **Round 2**: Models refined their critiques after seeing others' perspectives
- **Synthesis**: GPT-OSS created a comprehensive final analysis

**Key Insights from the Demo:**
- Identified consensus on strong points (compelling vision, historical analogies)
- Highlighted overlooked risks (inequality, governance, misalignment)
- Provided actionable recommendations for strengthening the arguments

See `demo_results/` for full output.

## Use Cases

- **Academic Research** - Get multi-perspective feedback on papers, proposals, theses
- **Business Strategy** - Evaluate business plans, strategy documents, proposals
- **Policy Analysis** - Assess policy documents, white papers, regulations
- **Content Evaluation** - Critique essays, articles, speeches
- **Technical Documentation** - Review technical specs, architecture docs

## Project Structure

```
delphi-ai-critique/
├── delphi_critique.py          # Main system code
├── demo_results/               # Example outputs
│   ├── intelligence_age_critique.docx
│   └── intelligence_age_critique.pdf
├── requirements.txt            # Dependencies
├── README.md                   # This file
└── examples/
    └── usage_examples.py       # More usage examples
```

## 🔧 Configuration

### Supported Input Formats
- PDF (`.pdf`)
- Word Documents (`.docx`)
- Plain Text (`.txt`)

### Supported Output Formats
- Plain Text (`.txt`)
- Word Document (`.docx`) - **Recommended for professional use**
- PDF (`.pdf`)

### Customization

You can customize the critique focus:

```python
# For research papers
task_instruction = """Evaluate the research methodology, 
theoretical framework, data analysis, and conclusions."""

# For business documents
task_instruction = """Assess the market analysis, 
financial projections, competitive positioning, and strategic risks."""

# For policy documents
task_instruction = """Analyze the policy objectives, 
implementation feasibility, stakeholder impacts, and potential unintended consequences."""
```

## The Delphi Technique Connection

This system is inspired by the [Delphi technique](https://en.wikipedia.org/wiki/Delphi_method) used in organizational decision-making:

| Traditional Delphi | Delphi-AI System |
|-------------------|------------------|
| Panel of human experts | Panel of diverse LLMs |
| Anonymous responses | Independent model critiques |
| Iterative rounds with feedback | Two-round refinement process |
| Facilitator synthesizes | GPT-OSS synthesizes |
| Aims for consensus | Identifies consensus + contradictions |

## 📈 Why Multiple Models?

Different LLMs have different strengths:
- **Llama 3.3** - Strong at reasoning and logical analysis
- **DeepSeek** - Excellent at technical depth and detail
- **Qwen** - Good at holistic perspectives and context
- **GPT-OSS** - Effective at synthesis and pattern recognition

Using multiple models captures blind spots that any single model would miss.

## Contributing

Contributions welcome! Areas for improvement:
- Add more LLM options (Claude, Gemini, etc.)
- Implement 3+ round iterations
- Add specialized critique templates for different domains
- Create interactive web interface
- Add visualization of consensus/disagreement patterns

## License

MIT License - feel free to use and modify for your projects.

## Contact

Questions or feedback? Open an issue or reach out!

---

**⭐ If you find this useful, please star the repository!**
