# Student Quick Start Guide

Welcome to the Azure Communication Services Call Automation Capstone Project! This guide will help you get started quickly.

## 🎯 Quick Links

- **Main Project Plan:** [CAPSTONE_PROJECT_PLAN.md](./CAPSTONE_PROJECT_PLAN.md)
- **Technical Documentation:** [CallAutomation_OutboundCalling/README.md](./CallAutomation_OutboundCalling/README.md)
- **Contributing Guidelines:** [CONTRIBUTING.md](./CONTRIBUTING.md)

## 📋 Pre-Flight Checklist

Before your first team meeting, complete these items:

- [ ] Read this entire document
- [ ] Review the [CAPSTONE_PROJECT_PLAN.md](./CAPSTONE_PROJECT_PLAN.md)
- [ ] Set up your development environment (see below)
- [ ] Join the team communication channel
- [ ] Introduce yourself to your team

## 🚀 Development Environment Setup (Week 1)

### Required Software

1. **Node.js** (v14 or higher)
   ```bash
   # Check if installed
   node --version
   npm --version
   ```
   Download from: https://nodejs.org/

2. **Visual Studio Code**
   - Download from: https://code.visualstudio.com/
   - Recommended Extensions:
     - TypeScript
     - ESLint
     - Azure Account
     - Azure Tools

3. **Git**
   ```bash
   # Check if installed
   git --version
   ```
   Download from: https://git-scm.com/

4. **Azure CLI** (Optional but recommended)
   ```bash
   # Check if installed
   az --version
   ```
   Download from: https://learn.microsoft.com/cli/azure/install-azure-cli

### Initial Setup Steps

1. **Fork and Clone the Repository**
   ```bash
   # Clone the repository
   git clone https://github.com/vinod-soni-microsoft/acs-capstone.git
   cd acs-capstone/CallAutomation_OutboundCalling
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Verify Installation**
   ```bash
   npm run build
   ```
   If this succeeds, you're ready to go! 🎉

## 🔐 Azure Account Setup (Week 1-2)

### Option 1: Azure for Students (Recommended)
- Visit: https://azure.microsoft.com/free/students/
- Free $100 credit (no credit card required)
- Perfect for this project

### Option 2: Azure Free Trial
- Visit: https://azure.microsoft.com/free/
- Free $200 credit for 30 days
- Requires credit card for verification

### Required Azure Resources

You'll need to create these resources in Azure:

1. **Azure Communication Services Resource**
   - Provides calling capabilities
   - Costs: ~$0.004 per minute for PSTN calls
   - Budget Tip: Use short test calls

2. **Phone Number**
   - Acquired through ACS
   - Costs: ~$0.40-1.00/month depending on location
   - Budget Tip: Release when not actively developing

3. **Azure AI Multi Service**
   - Provides Text-to-Speech and Speech-to-Text
   - Free tier available (5 million characters/month)
   - Perfect for development and testing

### Budget Management
- Set up cost alerts in Azure Portal
- Expected total cost for 12 weeks: **$10-30**
- Daily development: ~$0.50-1.00
- Release resources when not in use

## 📚 Learning Path

### Week 1-2: Getting Started
- [ ] Complete environment setup
- [ ] Read Azure ACS documentation
- [ ] Understand the existing codebase
- [ ] Make your first test call

### Week 3-5: Core Development
- [ ] Configure Azure resources
- [ ] Enhance IVR system
- [ ] Customize voice prompts
- [ ] Test thoroughly

### Week 6-8: Advanced Features
- [ ] Add database integration
- [ ] Implement advanced call features
- [ ] Focus on security
- [ ] Document everything

### Week 9-10: Quality Assurance
- [ ] Write comprehensive tests
- [ ] Optimize performance
- [ ] Fix bugs
- [ ] Code review

### Week 11-12: Finalization
- [ ] Deploy to Azure
- [ ] Complete documentation
- [ ] Prepare presentation
- [ ] Submit project

## 🛠️ Essential Commands

### Development
```bash
# Run in development mode (with auto-reload)
npm run dev

# Build TypeScript
npm run build

# Format code (if configured)
npm run format

# Lint code (if configured)
npm run lint
```

### Git Workflow
```bash
# Create a new feature branch
git checkout -b feature/your-feature-name

# Stage changes
git add .

# Commit changes
git commit -m "Description of changes"

# Push to remote
git push origin feature/your-feature-name

# Create Pull Request on GitHub
```

### Azure DevTunnel (for webhook testing)
```bash
# Create tunnel
devtunnel create --allow-anonymous

# Create port
devtunnel port create -p 8080

# Host tunnel
devtunnel host
```

## 📖 Key Concepts to Understand

### 1. Call Automation Flow
```
User Dials In → ACS Receives Call → Your App (Webhook) 
→ Play Audio → Recognize Input → Process Response 
→ Take Action → End Call
```

### 2. Event-Driven Architecture
- Your application responds to events from ACS
- Events are sent via webhooks to your callback URL
- Common events: CallConnected, RecognizeCompleted, CallDisconnected

### 3. IVR (Interactive Voice Response)
- Menu system for phone calls
- Uses Text-to-Speech to play prompts
- Recognizes user input (voice or DTMF tones)
- Routes calls based on responses

## 🎓 Best Practices

### Code Quality
- ✅ Write clean, readable code
- ✅ Add comments for complex logic
- ✅ Follow TypeScript best practices
- ✅ Use meaningful variable names
- ✅ Keep functions small and focused

### Git Practices
- ✅ Commit often with clear messages
- ✅ Create feature branches
- ✅ Pull before pushing
- ✅ Review code before merging
- ✅ Keep commits atomic

### Security
- ⚠️ **NEVER** commit credentials
- ⚠️ Use environment variables
- ⚠️ Add `.env` to `.gitignore`
- ⚠️ Use Azure Key Vault for production
- ⚠️ Validate all user inputs

### Testing
- ✅ Test on real phone numbers
- ✅ Test various input scenarios
- ✅ Document test results
- ✅ Test error cases
- ✅ Keep test data organized

## 🤝 Team Collaboration

### Roles & Responsibilities

**Team Lead**
- Coordinate tasks and timeline
- Run team meetings
- Communicate with instructor
- Track overall progress

**Backend Developer**
- Focus on ACS integration
- Implement call logic
- Database integration
- API development

**Frontend/Integration Developer**
- Web interface development
- Azure services integration
- User experience
- Configuration management

**QA/DevOps Engineer**
- Testing and quality assurance
- Deployment setup
- Monitoring and logging
- Documentation review

### Meeting Structure

**Monday Planning (30 min)**
- Review last week's progress
- Plan this week's tasks
- Assign responsibilities
- Identify blockers

**Wednesday Sync (30 min)**
- Progress updates
- Problem solving
- Technical discussions
- Help requests

**Friday Demo (45 min)**
- Demonstrate completed work
- Retrospective (what went well, what to improve)
- Prepare for next week
- Update project board

## 📝 Documentation Tips

### What to Document
- Setup instructions
- Configuration steps
- API usage examples
- Design decisions
- Known issues
- Testing procedures

### How to Document
- Use Markdown for consistency
- Include code examples
- Add screenshots where helpful
- Keep it updated
- Make it searchable

## 🔧 Troubleshooting

### Common Issues

**Issue:** `npm install` fails
- **Solution:** Delete `node_modules` and `package-lock.json`, then run `npm install` again

**Issue:** Can't connect to Azure DevTunnel
- **Solution:** Check if tunnel is running with `devtunnel list`, restart if needed

**Issue:** Call doesn't connect
- **Solution:** Verify phone numbers are in E.164 format (e.g., +14255551234)

**Issue:** No audio in call
- **Solution:** Check Cognitive Services endpoint in `.env` file

**Issue:** Webhook not receiving events
- **Solution:** Ensure callback URL is publicly accessible and using HTTPS

### Getting Help

1. **Check Documentation**
   - Project README
   - Azure documentation
   - Error messages

2. **Ask Your Team**
   - Team chat
   - Team meetings
   - Pair programming

3. **Ask Instructor**
   - Office hours
   - Email
   - Class time

4. **Search Online**
   - Stack Overflow
   - Microsoft Q&A
   - GitHub Issues

## 🎯 Week-by-Week Focus

| Week | Focus Area | Key Deliverable |
|------|------------|----------------|
| 1-2 | Setup & Learning | Environment ready, Azure account |
| 3-5 | Core Features | Working call system with IVR |
| 6-8 | Advanced Features | Database, security, advanced calls |
| 9-10 | Testing & QA | Test suite, optimized code |
| 11-12 | Polish & Present | Deployed app, documentation, presentation |

## 📊 Success Indicators

You're on track if:
- ✅ You can make a test call by Week 3
- ✅ You have a custom IVR menu by Week 5
- ✅ You have database integration by Week 7
- ✅ You have tests running by Week 9
- ✅ You're deployed to Azure by Week 11

## 🌟 Tips for Success

1. **Start Early:** Don't wait until the deadline
2. **Communicate:** Keep your team informed
3. **Test Often:** Catch issues early
4. **Document:** Future you will thank present you
5. **Ask Questions:** There are no stupid questions
6. **Have Fun:** This is a cool project!

## 📚 Additional Resources

### Azure Learning Paths
- [Azure Communication Services Learning Path](https://learn.microsoft.com/training/paths/azure-communication-services/)
- [Azure Fundamentals](https://learn.microsoft.com/training/paths/az-900-describe-cloud-concepts/)

### TypeScript Resources
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [TypeScript Deep Dive](https://basarat.gitbook.io/typescript/)

### Node.js Resources
- [Node.js Documentation](https://nodejs.org/docs/)
- [Express.js Guide](https://expressjs.com/en/guide/routing.html)

### Testing Resources
- [Jest Documentation](https://jestjs.io/docs/getting-started)
- [Testing Best Practices](https://github.com/goldbergyoni/javascript-testing-best-practices)

## 💬 Community

- **Class Discord/Slack:** [Link to be provided]
- **Office Hours:** [Schedule to be provided]
- **Instructor Email:** [Email to be provided]

---

## ✨ You've Got This!

Remember, this project is designed to be challenging but achievable. Take it one week at a time, communicate with your team, and don't hesitate to ask for help when needed.

**Good luck, and happy coding!** 🚀

---

**Last Updated:** January 2026  
**Version:** 1.0
