# 📇 Quick Reference Card - CrewAI Interview Coach

## 🎯 7 Agents at a Glance

| Agent | Role | Purpose | Output |
|-------|------|---------|--------|
| 🔍 Research | Corporate Intelligence Researcher | Company & interviewer research | Intelligence brief |
| 📄 Resume Analyzer | Talent Assessment Specialist | Gap analysis & STAR stories | Match score + positioning |
| ❓ Question Generator | Interview Design Architect | Contextual question creation | 15 categorized questions |
| 👔 HR Screening | HR Recruiter | Initial screening interview | Interactive Q&A |
| 💻 Technical | Senior Technical Lead | Technical competency assessment | Interactive Q&A |
| 🗣️ Behavioral | Hiring Manager | Soft skills & culture fit | Interactive Q&A |
| 🎓 Coach | Executive Interview Coach | Comprehensive feedback | Scores + improvements |

---

## ⚡ Quick Commands

### Setup
```python
!pip install 'crewai[tools]' -q
os.environ['OPENAI_API_KEY'] = userdata.get('ai_agents_openai')
```

### Run Full Interview
```python
result = interview_crew.kickoff()
```

### Display Feedback
```python
display(Markdown(result.tasks_output[-1].raw))
```

### Focused Technical Practice
```python
technical_crew = Crew(
    agents=[question_generator_agent, technical_interviewer_agent, interview_coach_agent],
    tasks=[question_generation_task, technical_interview_task, coaching_task],
    process=Process.sequential,
    memory=True
)
technical_result = technical_crew.kickoff()
```

---

## 📊 Scoring Guide

| Score | Meaning | Action |
|-------|---------|--------|
| 9-10 | Exceptional | Ready for senior roles |
| 7-8 | Strong | Competitive for target role |
| 5-6 | Good foundation | Focused improvement needed |
| 3-4 | Developing | Significant practice required |
| 1-2 | Early stage | Consider role level fit |

---

## 🎓 Interview Tips Cheat Sheet

### STAR Method Template
- **S**ituation: Set the context (2-3 sentences)
- **T**ask: Your responsibility or challenge
- **A**ction: What YOU specifically did (most important)
- **R**esult: Quantifiable outcome + learning

### Technical Interview
✅ Think aloud | Ask clarifications | Discuss trade-offs | Optimize iteratively  
❌ Jump to code | Pretend knowledge | Ignore hints | Single solution focus

### Behavioral Interview  
✅ Specific examples | "I" not "we" | Include failures | Quantify results  
❌ Vague/theoretical | Take all credit | Avoid challenges | Ramble

### HR Screening
✅ Show research | Genuine enthusiasm | Thoughtful questions | Honesty  
❌ Generic answers | Bad-mouth others | Salary-only focus | Rush

---

## 📁 Documentation Map

| File | Lines | Purpose |
|------|-------|---------|
| IMPLEMENTATION_SUMMARY.md | 400+ | What was built & how to use it |
| PROMPTS_DOCUMENTATION.md | 650+ | Prompt engineering deep-dive |
| PROMPT_TEMPLATES.md | 600+ | Industry/role variations |
| USAGE_GUIDE.md | 450+ | Practical how-to guide |
| README.md | 285+ | Project overview |
| **TOTAL** | **2,385+** | **Comprehensive docs** |

---

## 🔧 Common Customizations

### Change Interviewer Personality
```python
backstory += "Your style is [warm/challenging/direct]..."
```

### Adjust Question Difficulty
```python
description = "Generate [easier/harder] questions focusing on..."
```

### Add Industry Context
```python
# See PROMPT_TEMPLATES.md for:
- Startup variants
- Enterprise variants  
- Consulting variants
- FAANG variants
```

### Focus on Specific Skills
```python
description = "Focus on: cloud architecture, team leadership, conflict resolution..."
```

---

## ⏱️ Time Estimates

| Activity | Duration |
|----------|----------|
| Setup | 5 min |
| Full interview | 30-45 min |
| Technical only | 15-20 min |
| Behavioral only | 15-20 min |
| Review feedback | 5-10 min |

---

## 🚨 Troubleshooting

| Issue | Solution |
|-------|----------|
| API key error | Check Colab secrets, manually set `os.environ['OPENAI_API_KEY']` |
| Generic questions | Provide detailed job description, add your resume |
| Rate limit | Wait 60s, reduce verbose output |
| Import error | `!pip install 'crewai[tools]' -q` |

---

## 💡 Pro Tips

1. **Treat it like real interview** - No pausing to Google
2. **Time yourself** - 2-3 min per answer max
3. **Run 3+ sessions** - Track improvement over time
4. **Focus practice** - Use targeted crews for weak spots
5. **Update materials** - Refine STAR stories based on feedback

---

## 🎯 Success Metrics

After using this system, you should:
- ✅ Have 5+ polished STAR stories ready
- ✅ Know your top 3 strengths and how to articulate them
- ✅ Understand potential concerns and how to address them
- ✅ Have company-specific questions prepared
- ✅ Feel confident in interview performance
- ✅ See score improvement across practice sessions

---

## 📞 Support Resources

- **CrewAI Docs**: https://docs.crewai.com/
- **OpenAI API**: https://platform.openai.com/docs
- **SERPER API**: https://serper.dev/
- **STAR Method**: Search "STAR interview method guide"
- **System Design**: github.com/donnemartin/system-design-primer

---

**🚀 Quick Start: Open notebook → Set API keys → Run interview_crew.kickoff() → Review feedback!**

*Your interview preparation AI team is ready to help you succeed!* 🎯
