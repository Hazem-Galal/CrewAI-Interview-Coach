# 🎯 CrewAI Interview Coach - Multi-Agent Interview Preparation System

An advanced AI-powered interview preparation platform using CrewAI's multi-agent orchestration and OpenAI's GPT-4o to provide realistic, comprehensive interview practice with expert coaching feedback.

## 🌟 Features

### Multi-Agent Architecture (7 Specialized Agents)

1. **Research Agent** 🔍
   - Investigates target company culture, recent news, and market position
   - Researches interviewer background and style
   - Provides strategic insights for demonstrating cultural fit

2. **Resume Analyzer Agent** 📄
   - Maps candidate qualifications to job requirements
   - Identifies strengths and potential gaps
   - Extracts STAR stories from background
   - Provides strategic positioning recommendations

3. **Question Generator Agent** ❓
   - Creates contextual, non-repetitive interview questions
   - Generates progressive difficulty technical questions
   - Designs behavioral questions using STAR methodology
   - Adapts questions based on company research and candidate background

4. **HR Screening Agent** 👔
   - Conducts initial screening interviews
   - Assesses motivation and basic qualifications
   - Evaluates cultural fit and expectations alignment
   - Warm, professional communication style

5. **Technical Interviewer Agent** 💻
   - Deep-dive technical assessments
   - Problem-solving and system design scenarios
   - Adaptive difficulty based on candidate responses
   - Collaborative problem-solving approach

6. **Behavioral Interviewer Agent** 🗣️
   - STAR-format behavioral questions
   - Assesses leadership, communication, adaptability
   - Probes for specificity and authenticity
   - Evaluates learning from failures

7. **Interview Coach Agent** 🎓
   - Comprehensive multi-dimensional feedback
   - Specific, actionable improvement strategies
   - Scoring across technical, communication, and cultural fit
   - Industry-specific insider tips

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- OpenAI API key
- (Optional) SERPER API key for web search capabilities

### Installation

```bash
# Install required packages
pip install 'crewai[tools]' langchain-openai
```

### Usage in Google Colab

1. **Set up API Keys**
   - Store your OpenAI API key in Colab secrets as `ai_agents_openai`
   - (Optional) Store SERPER API key as `serper_api_key`

2. **Input Interview Details**
   - Interviewer name
   - Company name
   - Job position
   - Job description
   - Your resume/background (optional)

3. **Run the Interview Preparation**
   - The system will automatically:
     - Research the company and interviewer
     - Analyze your background
     - Generate contextual questions
     - Conduct multi-stage interviews (HR, Technical, Behavioral)
     - Provide comprehensive coaching feedback

## 📊 Workflow

```
┌─────────────────────────────────────────────────────────────┐
│                     RESEARCH PHASE                          │
│  ┌──────────────────┐         ┌──────────────────┐        │
│  │ Research Agent   │         │ Resume Analyzer  │        │
│  │ (Company/Person) │         │ (Gap Analysis)   │        │
│  └──────────────────┘         └──────────────────┘        │
└───────────────────┬─────────────────┬───────────────────────┘
                    │                 │
                    ▼                 ▼
            ┌──────────────────────────────────┐
            │   PLANNING PHASE                 │
            │   Question Generator Agent       │
            │   (Contextual Questions)         │
            └────────────┬─────────────────────┘
                         │
                         ▼
            ┌──────────────────────────────────┐
            │   INTERVIEW PHASE (Sequential)   │
            │   ┌────────────────────────┐     │
            │   │ 1. HR Screening        │     │
            │   │ 2. Technical Interview │     │
            │   │ 3. Behavioral Interview│     │
            │   └────────────────────────┘     │
            └────────────┬─────────────────────┘
                         │
                         ▼
            ┌──────────────────────────────────┐
            │   COACHING PHASE                 │
            │   Interview Coach Agent          │
            │   (Comprehensive Feedback)       │
            └──────────────────────────────────┘
```

## 🎯 Key Differentiators

### Authentic Prompts
- **No Generic Templates**: Each agent has unique personality and methodology
- **Context-Aware**: Questions reference company research and candidate background
- **Progressive Depth**: Conversations build naturally, not scripted Q&A
- **Industry-Specific**: Adapts to role requirements and company culture

### Multi-Dimensional Assessment
- **Content Quality**: Relevance, specificity, technical accuracy
- **Communication Excellence**: Clarity, confidence, active listening
- **Strategic Positioning**: Addressing gaps, demonstrating fit
- **Scored Feedback**: Quantitative ratings with qualitative justification

### Flexible Architecture
- **Full Interview Simulation**: Run complete multi-stage interview
- **Focused Practice**: Run individual components (technical-only, behavioral-only)
- **Memory Integration**: Builds conversation history across sessions
- **Adaptive Difficulty**: Adjusts based on candidate responses

## 📝 Example Output

### Research Brief
```
Top 3 Company Insights:
- Recently launched AI-powered analytics platform (Q4 2025)
- Strong emphasis on data-driven decision making culture
- Expanding European presence with new Berlin office

Interviewer Background:
- 15+ years in data engineering and cloud architecture
- Frequent speaker on DBT best practices
- Values pragmatic solutions over perfect architecture
```

### Coaching Feedback Format
```
✅ What Worked Well
- Strong STAR structure in conflict resolution story
- Demonstrated technical depth in DBT modeling discussion
- Authentic enthusiasm for company mission

⚠️ Areas for Improvement
- Add quantifiable metrics to impact statements
- Address 6-month gap proactively in opening
- Slow down when explaining complex technical concepts

🎯 Next-Level Actions
- Practice 30-second elevator pitch with specific numbers
- Prepare "what I learned during career transition" narrative
- Record yourself and work on pacing

📊 Overall Score: 7.5/10
Technical: 8/10 | Communication: 7/10 | Cultural Fit: 8/10
```

## 🔧 Customization

### Adjust Agent Personalities
Modify the `backstory` parameter in each agent to change interview style:
```python
hr_screening_agent = Agent(
    role="HR Recruiter",
    backstory="Your custom interviewer personality..."
)
```

### Modify Question Frameworks
Edit task descriptions to emphasize different competencies:
```python
question_generation_task = Task(
    description="Focus on: [your key competencies]..."
)
```

### Change Orchestration
Switch between sequential, hierarchical, or parallel processing:
```python
interview_crew = Crew(
    process=Process.hierarchical  # or Process.sequential
)
```

## 🛠️ Advanced Features

### Multiple Interview Rounds
Run focused sessions for specific stages:
```python
technical_crew = Crew(
    agents=[technical_interviewer_agent, coach_agent],
    tasks=[technical_task, coaching_task]
)
```

### Knowledge Source Integration
Build conversation history across sessions:
```python
string_source = StringKnowledgeSource(content=interview_history)
crew = Crew(knowledge_sources=[string_source])
```

## 📚 Resources

- [CrewAI Documentation](https://docs.crewai.com/)
- [OpenAI API Reference](https://platform.openai.com/docs)
- [SERPER API](https://serper.dev/) for web search

## 🤝 Contributing

Contributions welcome! Areas for enhancement:
- Additional interviewer personas (FAANG, startup, consulting)
- Industry-specific question templates
- Integration with video interview simulation
- Multi-language support

## 📄 License

MIT License - feel free to use and modify for your interview preparation needs.

## 🎓 Interview Preparation Tips

1. **Be Specific**: Use concrete examples with numbers and outcomes
2. **STAR Method**: Structure behavioral answers (Situation, Task, Action, Result)
3. **Research Deeply**: Know the company beyond the homepage
4. **Ask Questions**: Demonstrate curiosity and strategic thinking
5. **Practice Regularly**: Use this tool multiple times to build confidence

---

**Built with CrewAI, OpenAI GPT-4o, and a passion for helping people land their dream jobs! 🚀**