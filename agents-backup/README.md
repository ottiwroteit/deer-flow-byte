# OTTI Agents Backup

Version-controlled mirror of OTTI's 43 custom DeerFlow agents.

The live runtime copies live in `backend/.deer-flow/users/{user_id}/agents/` (gitignored).
This folder is the portable, version-controlled backup so the SOULs travel with the repo.

## Restore on a new machine

```bash
# 1. Find your user_id (after signing up to DeerFlow locally)
sqlite3 backend/.deer-flow/data/deerflow.db "SELECT id, email FROM users;"

# 2. Copy the backup into your runtime user dir
USER_ID=<your-user-id>
mkdir -p backend/.deer-flow/users/$USER_ID/agents
cp -r agents-backup/* backend/.deer-flow/users/$USER_ID/agents/

# 3. Make sure agents_api.enabled = true in config.yaml
# 4. Restart the gateway: make stop && make dev
# 5. Refresh http://localhost:2026/workspace/agents
```

## Roster

**Research (5):** competitor-teardown · niche-scout · ad-creative-scout · aso-analyst · customer-voice-miner

**Strategy & Audit (3):** prd-drafter · pre-launch-auditor · weekly-portfolio-strategist

**App Store / Mobile Marketing (4):** app-store-copywriter · ad-script-writer · influencer-outreach-drafter · email-sequence-writer

**Web / Landing / SEO (3):** landing-page-writer · seo-specialist · conversion-rate-optimizer

**Founder Brand (2):** linkedin-ghostwriter · twitter-ghostwriter

**PR & Distribution (2):** press-pitch-writer · partnership-scout

**B2B Sales (5):** icp-researcher · cold-email-specialist · sales-deck-builder · demo-script-writer · case-study-writer

**Ops (3):** revenue-analyst · review-responder · changelog-writer

**Strategy & Planning (1):** content-strategy-planner

**Legal (1):** legal-doc-drafter

**Intelligence & Trends (6):** universal-scraper · github-trend-scout · global-tech-scout · ai-frontier-tracker · spatial-3d-scout · x-twitter-listener

**Engineering Offload (5):** code-reviewer · security-auditor · dependency-monitor · bug-triager · release-coordinator

**Knowledge & Context (3):** documentation-keeper · stack-news-digest · decision-journaler

## Companion Claude Code skills

For OTTI's full Apify integration, install in Claude Code:

```bash
claude plugin marketplace add https://github.com/apify/agent-skills
claude plugin install apify-ultimate-scraper@apify-agent-skills
claude plugin install apify-actor-development@apify-agent-skills
claude plugin install apify-actorization@apify-agent-skills
claude plugin install apify-generate-output-schema@apify-agent-skills
brew install apify-cli
```
