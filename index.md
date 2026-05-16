<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Salesforce Team Lead — Interview Prep Guide</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500;9..40,600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --bg: #0d1117; --bg-card: #161b22; --bg-elevated: #21262d;
      --border: rgba(48,54,61,0.9); --text: #f0f6fc; --text-muted: #8b949e; --text-dim: #6e7681;
      --blue: #58a6ff; --green: #3fb950; --orange: #d29922; --red: #f85149;
      --purple: #bc8cff; --cyan: #39d5d5; --yellow: #e3b341;
    }
    html { scroll-behavior: smooth; }
    body { background: var(--bg); color: var(--text); font-family: 'DM Sans', sans-serif; font-size: 15px; line-height: 1.6; min-height: 100vh; }
    ::-webkit-scrollbar { width: 7px; height: 7px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--bg-elevated); border-radius: 4px; }
    ::-webkit-scrollbar-thumb:hover { background: #30363d; }

    /* NAV */
    .nav { position: sticky; top: 0; z-index: 100; background: rgba(13,17,23,0.88); backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px); border-bottom: 1px solid var(--border); padding: 0 24px; }
    .nav-inner { max-width: 1240px; margin: 0 auto; display: flex; align-items: center; gap: 28px; height: 58px; }
    .nav-logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 17px; color: var(--blue); text-decoration: none; white-space: nowrap; letter-spacing: -0.5px; cursor: pointer; }
    .nav-logo span { color: var(--text-muted); font-weight: 400; }
    .nav-links { display: flex; gap: 2px; flex: 1; overflow-x: auto; scrollbar-width: none; }
    .nav-links::-webkit-scrollbar { display: none; }
    .nav-link { padding: 6px 12px; border-radius: 6px; color: var(--text-muted); text-decoration: none; font-size: 13px; font-weight: 500; white-space: nowrap; transition: color .15s, background .15s; cursor: pointer; border: none; background: none; font-family: 'DM Sans', sans-serif; }
    .nav-link:hover { color: var(--text); background: var(--bg-elevated); }
    .nav-progress { font-size: 12px; color: var(--text-muted); white-space: nowrap; background: var(--bg-elevated); padding: 4px 12px; border-radius: 20px; border: 1px solid var(--border); }
    .nav-progress strong { color: var(--green); }

    /* HERO */
    .hero { padding: 80px 24px 60px; max-width: 1240px; margin: 0 auto; position: relative; overflow: hidden; }
    .hero-glow { position: absolute; top: -60px; right: -80px; width: 500px; height: 500px; background: radial-gradient(circle, rgba(88,166,255,0.07) 0%, transparent 65%); pointer-events: none; }
    .hero-glow2 { position: absolute; bottom: 0; left: 10%; width: 300px; height: 200px; background: radial-gradient(circle, rgba(63,185,80,0.04) 0%, transparent 70%); pointer-events: none; }
    .hero-eyebrow { font-family: 'JetBrains Mono', monospace; font-size: 11.5px; color: var(--blue); letter-spacing: 2.5px; text-transform: uppercase; margin-bottom: 18px; display: flex; align-items: center; gap: 10px; }
    .hero-eyebrow::before { content: ''; display: inline-block; width: 28px; height: 1px; background: var(--blue); }
    .hero h1 { font-family: 'Syne', sans-serif; font-weight: 800; font-size: clamp(36px, 5.5vw, 68px); line-height: 1.02; letter-spacing: -2.5px; margin-bottom: 20px; }
    .hero h1 .accent { color: var(--blue); }
    .hero-desc { font-size: 16.5px; color: var(--text-muted); max-width: 580px; line-height: 1.75; margin-bottom: 36px; }
    .hero-stats { display: flex; gap: 32px; flex-wrap: wrap; }
    .stat-num { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 30px; color: var(--blue); line-height: 1; }
    .stat-label { font-size: 12.5px; color: var(--text-muted); margin-top: 2px; }

    /* SECTION */
    .section { max-width: 1240px; margin: 0 auto; padding: 64px 24px; border-top: 1px solid var(--border); }
    .section-label { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: var(--blue); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 8px; display: block; }
    .section-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 30px; letter-spacing: -0.5px; line-height: 1.2; }
    .section-desc { color: var(--text-muted); margin-top: 8px; font-size: 14px; }
    .section-header { margin-bottom: 32px; }

    /* FILTER */
    .filters { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 28px; align-items: center; }
    .filter-btn { padding: 6px 15px; border-radius: 20px; border: 1px solid var(--border); background: transparent; color: var(--text-muted); font-size: 13px; font-family: 'DM Sans', sans-serif; font-weight: 500; cursor: pointer; transition: all .15s; white-space: nowrap; }
    .filter-btn:hover { border-color: var(--blue); color: var(--blue); }
    .filter-btn.active { background: var(--blue); border-color: var(--blue); color: #0d1117; font-weight: 600; }
    .filter-count { font-size: 13px; color: var(--text-muted); margin-left: auto; white-space: nowrap; }

    /* CARDS */
    .cards-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(480px, 1fr)); gap: 14px; }
    @media (max-width: 680px) { .cards-grid { grid-template-columns: 1fr; } }
    .interview-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 12px; padding: 22px; transition: border-color .2s, transform .2s, box-shadow .2s; display: flex; flex-direction: column; gap: 14px; }
    .interview-card:hover { border-color: rgba(88,166,255,0.28); transform: translateY(-1px); box-shadow: 0 4px 24px rgba(0,0,0,0.3); }
    .interview-card.reviewed { border-color: rgba(63,185,80,0.3); background: rgba(63,185,80,0.015); }
    .card-header { display: flex; align-items: flex-start; justify-content: space-between; gap: 10px; }
    .card-badges { display: flex; gap: 6px; flex-wrap: wrap; flex: 1; }
    .badge { font-size: 10.5px; font-weight: 700; padding: 3px 8px; border-radius: 4px; letter-spacing: 0.3px; font-family: 'JetBrains Mono', monospace; }
    .badge-must { background: rgba(248,81,73,0.12); color: var(--red); border: 1px solid rgba(248,81,73,0.3); }
    .badge-important { background: rgba(210,153,34,0.12); color: var(--orange); border: 1px solid rgba(210,153,34,0.3); }
    .badge-good { background: rgba(63,185,80,0.12); color: var(--green); border: 1px solid rgba(63,185,80,0.3); }
    .badge-cat { background: var(--bg-elevated); color: var(--text-muted); border: 1px solid var(--border); }
    .review-check { width: 22px; height: 22px; border-radius: 50%; border: 1.5px solid var(--border); display: flex; align-items: center; justify-content: center; font-size: 11px; flex-shrink: 0; transition: all .2s; cursor: pointer; user-select: none; }
    .review-check.checked { background: var(--green); border-color: var(--green); color: #0d1117; font-weight: 700; }
    .card-title { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 15.5px; line-height: 1.3; }
    .card-points { list-style: none; display: flex; flex-direction: column; gap: 5px; }
    .card-points li { font-size: 13.5px; color: var(--text-muted); padding-left: 16px; position: relative; line-height: 1.5; }
    .card-points li::before { content: '▸'; position: absolute; left: 0; color: var(--blue); font-size: 10px; top: 4px; }
    .card-tip { background: rgba(88,166,255,0.055); border: 1px solid rgba(88,166,255,0.18); border-left: 3px solid var(--blue); border-radius: 0 6px 6px 0; padding: 10px 14px; font-size: 13px; color: var(--text-muted); line-height: 1.55; }
    .card-tip strong { color: var(--blue); }
    .card-actions { display: flex; gap: 8px; }
    .btn { padding: 8px 16px; border-radius: 6px; border: none; font-family: 'DM Sans', sans-serif; font-size: 13px; font-weight: 500; cursor: pointer; transition: all .15s; display: inline-flex; align-items: center; gap: 6px; white-space: nowrap; }
    .btn-primary { background: var(--blue); color: #0d1117; }
    .btn-primary:hover { background: #79b8ff; }
    .btn-secondary { background: var(--bg-elevated); color: var(--text-muted); border: 1px solid var(--border); }
    .btn-secondary:hover { color: var(--text); border-color: var(--text-muted); }
    .btn-success { background: rgba(63,185,80,0.12); color: var(--green); border: 1px solid rgba(63,185,80,0.3); }
    .btn-success:hover { background: rgba(63,185,80,0.22); }

    /* MODAL */
    .modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.72); backdrop-filter: blur(5px); z-index: 200; display: flex; align-items: center; justify-content: center; padding: 20px; }
    .modal { background: var(--bg-card); border: 1px solid rgba(88,166,255,0.2); border-radius: 16px; padding: 32px; max-width: 700px; width: 100%; max-height: 82vh; overflow-y: auto; position: relative; box-shadow: 0 20px 60px rgba(0,0,0,0.5); }
    .modal-close { position: absolute; top: 16px; right: 16px; width: 30px; height: 30px; border-radius: 6px; border: 1px solid var(--border); background: var(--bg-elevated); color: var(--text-muted); cursor: pointer; display: flex; align-items: center; justify-content: center; font-size: 15px; transition: all .15s; }
    .modal-close:hover { color: var(--text); }
    .modal-label { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: var(--blue); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 10px; }
    .modal-q { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 20px; margin-bottom: 22px; line-height: 1.3; }
    .modal-body { font-size: 14px; color: var(--text-muted); line-height: 1.75; }
    .modal-body h4 { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 14px; color: var(--text); margin: 18px 0 8px; letter-spacing: 0.2px; border-left: 2px solid var(--blue); padding-left: 10px; }
    .modal-body p { margin-bottom: 10px; }
    .modal-body ul { list-style: none; margin-bottom: 10px; }
    .modal-body ul li { padding-left: 18px; position: relative; margin-bottom: 6px; }
    .modal-body ul li::before { content: '▸'; position: absolute; left: 0; color: var(--blue); font-size: 10px; top: 5px; }
    .modal-body strong { color: var(--text); font-weight: 600; }
    .modal-body code { font-family: 'JetBrains Mono', monospace; font-size: 12px; background: var(--bg-elevated); padding: 2px 6px; border-radius: 4px; color: var(--cyan); }

    /* TABS */
    .tabs { display: flex; gap: 2px; border-bottom: 1px solid var(--border); margin-bottom: 24px; overflow-x: auto; scrollbar-width: none; }
    .tabs::-webkit-scrollbar { display: none; }
    .tab-btn { padding: 10px 16px; border: none; background: none; color: var(--text-muted); font-family: 'DM Sans', sans-serif; font-size: 13.5px; font-weight: 500; cursor: pointer; border-bottom: 2px solid transparent; white-space: nowrap; transition: all .15s; margin-bottom: -1px; }
    .tab-btn:hover { color: var(--text); }
    .tab-btn.active { color: var(--blue); border-bottom-color: var(--blue); }

    /* TABLE */
    .table-wrap { overflow-x: auto; border-radius: 10px; border: 1px solid var(--border); }
    table { width: 100%; border-collapse: collapse; font-size: 13px; }
    th { background: var(--bg-elevated); padding: 10px 16px; text-align: left; font-family: 'JetBrains Mono', monospace; font-size: 10.5px; font-weight: 500; color: var(--text-muted); letter-spacing: 0.5px; text-transform: uppercase; border-bottom: 1px solid var(--border); white-space: nowrap; }
    td { padding: 10px 16px; border-bottom: 1px solid rgba(48,54,61,0.5); vertical-align: top; line-height: 1.5; }
    tr:last-child td { border-bottom: none; }
    tr:hover td { background: rgba(88,166,255,0.025); }
    .td-type { font-weight: 600; color: var(--text); white-space: nowrap; min-width: 180px; }
    .td-cap { font-family: 'JetBrains Mono', monospace; font-size: 11.5px; color: var(--purple); white-space: nowrap; }
    .td-example { font-family: 'JetBrains Mono', monospace; font-size: 11.5px; color: var(--cyan); }
    .td-convention { color: var(--text-muted); min-width: 220px; }

    /* BEST PRACTICES */
    .practices-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(340px, 1fr)); gap: 12px; }
    @media (max-width: 500px) { .practices-grid { grid-template-columns: 1fr; } }
    .practice-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: 10px; padding: 20px; display: flex; gap: 16px; transition: border-color .2s, transform .2s; }
    .practice-card:hover { border-color: rgba(88,166,255,0.22); transform: translateY(-1px); }
    .practice-num { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 34px; color: var(--bg-elevated); line-height: 1; min-width: 44px; user-select: none; transition: color .2s; }
    .practice-card:hover .practice-num { color: rgba(88,166,255,0.25); }
    .practice-title { font-family: 'Syne', sans-serif; font-weight: 600; font-size: 15px; margin-bottom: 6px; }
    .practice-desc { font-size: 13px; color: var(--text-muted); line-height: 1.6; }
    .practice-code { font-family: 'JetBrains Mono', monospace; font-size: 11px; background: var(--bg-elevated); border-radius: 6px; padding: 10px 12px; margin-top: 10px; color: var(--cyan); overflow-x: auto; white-space: pre; line-height: 1.6; border: 1px solid var(--border); }

    /* LIMITS */
    .limit-sync { color: var(--blue); font-family: 'JetBrains Mono', monospace; font-size: 12px; white-space: nowrap; }
    .limit-async { color: var(--green); font-family: 'JetBrains Mono', monospace; font-size: 12px; white-space: nowrap; }
    .limit-highlight td:first-child::before { content: '★ '; color: var(--yellow); font-size: 10px; }
    .limit-highlight td { background: rgba(227,179,65,0.03); }
    .async-note { background: var(--bg-card); border: 1px solid var(--border); border-left: 3px solid var(--purple); border-radius: 0 8px 8px 0; padding: 12px 16px; font-size: 13px; color: var(--text-muted); margin-bottom: 20px; line-height: 1.6; }
    .async-note strong { color: var(--purple); }
    .limit-callout { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 16px; }
    .limit-callout-item { background: var(--bg-card); border: 1px solid var(--border); border-radius: 8px; padding: 12px 16px; font-size: 13px; flex: 1; min-width: 200px; }
    .limit-callout-item .lc-title { font-weight: 600; margin-bottom: 3px; }

    /* MATRIX CELL COLORS */
    .cell-yes { color: var(--green); font-family: 'JetBrains Mono', monospace; font-size: 12px; }
    .cell-no { color: var(--red); font-family: 'JetBrains Mono', monospace; font-size: 12px; }

    /* FOOTER */
    .footer { border-top: 1px solid var(--border); padding: 32px 24px; text-align: center; color: var(--text-dim); font-size: 13px; }
    .footer span { color: var(--blue); }

    @media (max-width: 600px) {
      .hero h1 { letter-spacing: -1.5px; }
      .hero-stats { gap: 20px; }
      .nav-inner { gap: 12px; }
      .modal { padding: 24px; }
    }
  </style>
</head>
<body>
<div id="root"></div>
<script type="text/babel" data-presets="react">
const { useState, useEffect } = React;

// ───────────────────────────────────────────────
// DATA
// ───────────────────────────────────────────────

const INTERVIEW_DATA = [
  {
    id: 'security', category: 'Security', priority: 'Must know',
    title: 'How do you manage security and data access?',
    points: [
      'Permission Sets over Profiles for feature access',
      'Permission Set Groups to bundle related permissions',
      'Field-Level Security enforced — test with a non-admin user, not just System Admin',
      'CRUD/FLS checks in Apex using Schema.sObjectType and stripInaccessible()',
      'Sharing rules and OWD reviewed for every new object',
      'With sharing on all Apex classes unless explicitly justified',
      'Sensitive fields encrypted using Salesforce Shield or Platform Encryption',
      'Named Credentials for all external auth — no passwords in code or custom settings',
    ],
    tip: "Know stripInaccessible() — it's the modern way to enforce FLS in Apex and interviewers love it.",
    answer: `<h4>Opening</h4><p>Start with the access control hierarchy: <strong>OWD → Role Hierarchy → Sharing Rules → Manual Sharing → Apex Sharing</strong>. This demonstrates you understand the layered model.</p><h4>Key Points</h4><ul><li><strong>Permission Sets vs Profiles:</strong> Profiles handle login and baseline access. Permission Sets handle feature access. This is the modern Salesforce model.</li><li><strong>stripInaccessible():</strong> <code>SObjectAccessDecision d = Security.stripInaccessible(AccessType.READABLE, results);</code> — strips fields the user can't see before returning data.</li><li><strong>with sharing:</strong> Declare on every Apex class to respect sharing rules. Exceptions must be documented and justified.</li><li><strong>Named Credentials:</strong> Centralises external auth, avoids secrets in code or Custom Settings.</li></ul><h4>Interview Closer</h4><p>Mention you always <strong>test security with a low-privilege user</strong>, not as System Admin — admins bypass FLS and sharing, so tests pass even with broken security.</p>`
  },
  {
    id: 'effort', category: 'Team Lead', priority: 'Important',
    title: 'How do you estimate effort for a Salesforce project?',
    points: [
      'Break down into epics → user stories → technical tasks',
      'T-shirt sizing or story points with your team, not solo estimates',
      'Add discovery/design spike tasks — don\'t skip the "how are we building this" phase',
      'Factor in: test writing, code review cycles, deployment windows, and UAT support',
      'Historical velocity from previous sprints as a baseline',
      'Identify external dependencies early (integration teams, data migration) — they always slip',
      'Buffer 20-30% for Salesforce-specific unknowns: governor limits, platform bugs, release windows',
    ],
    tip: "Show you think about the full delivery cycle, not just the coding time.",
    answer: `<h4>Opening</h4><p>Frame estimation as a <strong>team activity</strong>, not something you do alone. Accuracy improves dramatically when the people doing the work do the estimating.</p><h4>Your Process</h4><ul><li><strong>Decomposition:</strong> Epic → Story → Task. Stories should be independently deliverable and testable.</li><li><strong>Relative sizing:</strong> Reference cards: "a simple field change = 1 point" give the team a common anchor.</li><li><strong>Hidden work:</strong> Test writing (aim for 80%+ coverage), code review, deployment prep, UAT support — budget this explicitly, not implicitly.</li><li><strong>Salesforce buffer:</strong> 20–30% for governor limit surprises, seasonal release conflicts, and org-specific quirks.</li></ul><h4>What Impresses</h4><p>Talk about tracking <strong>velocity over sprints</strong> and using it to refine future estimates. Shows you run a data-informed team, not a gut-feel one.</p>`
  },
  {
    id: 'onboarding', category: 'Team Lead', priority: 'Good to know',
    title: 'How do you onboard a new Salesforce developer to your team?',
    points: [
      'Pair them with a buddy for the first two weeks — shadowing, not solo work',
      'Walk through the org architecture, data model, and key business processes on day one',
      'Assign a low-complexity first story to build confidence before complex work',
      'Share team conventions doc: naming standards, branching strategy, PR process',
      'Mandatory Trailhead paths relevant to your stack',
      'First PR reviewed with detailed comments — learning opportunity, not a gotcha',
    ],
    tip: "Shows leadership maturity. Mention you set clear expectations so they know what 'good' looks like.",
    answer: `<h4>Opening</h4><p>Onboarding is a <strong>30-90 day investment</strong> that determines how quickly someone reaches full productivity. Cutting corners here costs 3× the time later.</p><h4>Week 1</h4><ul><li>Org tour: data model, key objects, flows, integrations, known landmines</li><li>Dev environment setup checklist — nobody should be blocked by tooling on day one</li><li>Meet the business stakeholders — context, not just code</li></ul><h4>Weeks 2-4</h4><ul><li>First story: simple but real — goes through the full dev → review → deploy cycle</li><li>Shadow a senior on a complex story to see team standards in practice</li><li>Team conventions walkthrough: naming, branching, PR format, test standards</li></ul><h4>What Impresses</h4><p>Mention a written <strong>team conventions doc</strong>. It shows you've systematised quality, not left it as tribal knowledge.</p>`
  },
  {
    id: 'techdebt', category: 'Team Lead', priority: 'Important',
    title: 'How do you handle technical debt in a Salesforce org?',
    points: [
      'Maintain a technical debt backlog — visible to the team and stakeholders',
      'Negotiate 15-20% sprint capacity for debt reduction alongside feature work',
      'Prioritize debt that causes instability or blocks future features first',
      'Refactor incrementally — don\'t rewrite entire modules at once',
      'Dead code removal: inactive flows, unused fields, deprecated classes — they slow deployments',
      'Org health metrics: static analysis score, code coverage trend, PMD violation count',
      'Present business impact to leadership: "This is slowing down every feature we build"',
    ],
    tip: "Showing you can communicate tech debt to non-technical stakeholders is a senior leadership skill.",
    answer: `<h4>Opening</h4><p>Tech debt is inevitable. The leadership skill is <strong>making it visible and managed</strong>, not pretending it doesn't exist.</p><h4>Your System</h4><ul><li><strong>Backlog:</strong> Every debt item is a ticket — prioritised, estimated, visible. Not a mental list.</li><li><strong>Sprint allocation:</strong> 15-20% reserved for debt. Non-negotiable. Feature and debt work run in parallel.</li><li><strong>Triage:</strong> Fix debt that slows down other work first — high-drag, high-impact items.</li><li><strong>Metrics:</strong> PMD violations, code coverage trend, deployment times. Data makes the conversation with leadership easier.</li></ul><h4>Stakeholder Communication</h4><p>Never say "we need to clean up code." Say: <strong>"This technical debt is adding 2 days of effort to every new feature. Fixing it now pays back in 3 sprints."</strong></p>`
  },
  {
    id: 'release', category: 'Team Lead', priority: 'Must know',
    title: 'How do you manage a Salesforce release?',
    points: [
      'Release calendar aligned with Salesforce seasonal releases (Spring, Summer, Winter)',
      'Sandbox refresh strategy: Full sandbox for UAT, Partial for integration testing',
      'Pre-release checklist: run all tests, PMD scan, security review, stakeholder sign-off',
      'Deployment window: off-peak hours, maintenance page if needed',
      'Post-deployment verification: smoke tests, key metrics, user confirmation',
      'Rollback plan documented before every deployment',
      'Release notes communicated to end users before go-live',
    ],
    tip: "Know that Salesforce releases on a fixed seasonal cadence — align your release strategy around it.",
    answer: `<h4>Opening</h4><p>A release is not just a deployment — it's a <strong>coordinated event</strong> with stakeholders, testing, communication, and a fallback plan.</p><h4>Pre-Release</h4><ul><li>All tests passing (100% existing + new), PMD clean, security review done</li><li>UAT sign-off from business owners — not just the QA team</li><li>Release notes prepared and communicated — users should not be surprised</li></ul><h4>Deployment Day</h4><ul><li>Deploy in off-peak window (evenings or weekends for critical orgs)</li><li>Smoke test immediately post-deploy — top 5 user journeys</li><li>Rollback procedure documented and ready — not improvised under pressure</li></ul><h4>What Impresses</h4><p>Know the <strong>Salesforce seasonal cadence</strong>: Spring (Feb), Summer (May/Jun), Winter (Oct/Nov). Your internal releases must account for platform changes in those windows. Surprises here signal poor planning.</p>`
  },
  {
    id: 'lwc', category: 'LWC & UI', priority: 'Important',
    title: 'What are your LWC best practices?',
    points: [
      'Component decomposition — small, single-responsibility components',
      'Use wire adapters (@wire) for data fetching; avoid imperative Apex calls unless needed',
      'Lightning Data Service (LDS) for single-record CRUD — no Apex needed',
      'Never manipulate the DOM directly — use reactive properties and templates',
      'Communicate between components: CustomEvent upward, properties downward, LMS for unrelated',
      'Lazy load heavy components with dynamic import() or conditional rendering',
      'Accessibility: ARIA attributes, keyboard navigation, focus management',
      'Use SLDS design tokens, not hardcoded colors or sizes',
    ],
    tip: "Know the parent-child communication pattern cold: properties down, events up, LMS for unrelated components.",
    answer: `<h4>Opening</h4><p>LWC is a component framework built on web standards with <strong>reactive data binding</strong>. The shift from Aura is significant — less magic, more explicit contracts.</p><h4>Communication Pattern</h4><ul><li><strong>Parent → Child:</strong> <code>@api</code> properties. Parent sets, child reacts.</li><li><strong>Child → Parent:</strong> <code>CustomEvent</code>. Child dispatches, parent listens via <code>oneventname</code>.</li><li><strong>Unrelated components:</strong> Lightning Message Service (LMS). Pub/sub across the page without a shared ancestor.</li></ul><h4>Data Access</h4><ul><li><strong>@wire:</strong> Reactive, cached, automatic refresh on data changes. Default choice.</li><li><strong>Imperative Apex:</strong> On button click, with error handling, sequential chained calls.</li><li><strong>LDS (getRecord, updateRecord):</strong> Single-record operations without Apex overhead.</li></ul><h4>What Impresses</h4><p>Mention <strong>SLDS design tokens</strong> and accessibility. Shows you build for real users in a real org, not just for demos.</p>`
  },
  {
    id: 'lwcperf', category: 'LWC & UI', priority: 'Good to know',
    title: 'How do you optimize LWC performance?',
    points: [
      'Wire caching — wire adapters cache by default, avoid bypassing unless you need fresh data',
      'Reduce Apex calls: cache responses in component state where appropriate',
      'Use @track sparingly — only for deep object/array mutations',
      'Virtual list rendering for large datasets (for:each with key attribute)',
      'Lazy-load components that aren\'t immediately visible',
      'Bundle size: avoid large JS libraries, use Salesforce base components',
      'Profile with Chrome DevTools and Lightning Component Profiler',
    ],
    tip: "Show you know the difference between @track (legacy), @api, and reactive assignment patterns.",
    answer: `<h4>Opening</h4><p>LWC performance problems are usually one of three things: <strong>too many Apex calls, too much DOM, or unnecessary re-renders</strong>. Fix those three and you've addressed 80% of issues.</p><h4>Reactivity in LWC</h4><ul><li><strong>Primitive assignment is reactive:</strong> <code>this.count = 5</code> triggers a re-render automatically.</li><li><strong>@track:</strong> Only needed for deep mutations inside objects or arrays. Often over-used.</li><li><strong>@api:</strong> Public properties exposed to parent. Never mutate directly inside the child component.</li></ul><h4>Performance Wins</h4><ul><li>Combine Apex calls into one method returning a wrapper class — fewer round-trips</li><li>Use <code>for:each</code> with <code>key</code> attribute — enables virtual list optimisation</li><li>Lazy load with <code>if:true</code> on a container, not repeated heavy components</li><li>Lightning Component Profiler in DevTools to identify slow renders</li></ul>`
  },
  {
    id: 'ldv', category: 'Data', priority: 'Important',
    title: 'How do you handle large data volumes (LDV) in Salesforce?',
    points: [
      'Design object models with skinny tables in mind — only frequently-queried fields',
      'Selective SOQL: always filter on indexed fields (Id, ExternalId, standard indexed fields)',
      'Custom indexes on fields used in WHERE clauses for high-volume queries',
      'Batch Apex for bulk processing — no trigger processing millions of records synchronously',
      'Archiving strategy: Big Objects for historical data, off-platform archiving for old records',
      'SOQL query plan tool to verify selectivity before deploying queries',
      'Avoid cross-object formula fields on LDV objects — they prevent skinny tables',
    ],
    tip: "Know that queries are selective when filters return < 10% of records or < 333K records (whichever is smaller).",
    answer: `<h4>Opening</h4><p>LDV problems manifest as timeouts, governor limit errors, and slow page loads. The fix is always <strong>better indexing + selective queries + async processing</strong>.</p><h4>Indexing Strategy</h4><ul><li>All WHERE clause fields on high-volume objects should be indexed — request custom index from Salesforce Support if needed</li><li>Avoid <code>OR</code> in SOQL — it can't use indexes. Use SOQL union patterns or separate queries instead</li><li>Avoid negative filters (<code>!=</code>, <code>NOT IN</code>) — they force full table scans</li></ul><h4>Data Architecture</h4><ul><li><strong>Skinny tables:</strong> Salesforce creates these automatically for SELECT-heavy objects. Avoid formula fields that block their creation.</li><li><strong>Big Objects:</strong> Unlimited archival storage, queryable via SOQL with some limitations. Good for audit logs and historical records.</li><li><strong>External archiving:</strong> Move records older than N years off-platform entirely — reduces org size and improves performance org-wide.</li></ul><h4>What Impresses</h4><p>Mention the <strong>SOQL Query Plan tool</strong> — using it proactively before deploying shows you prevent performance issues rather than react to them.</p>`
  },
  {
    id: 'migration', category: 'Data', priority: 'Good to know',
    title: 'What is your approach to data migration?',
    points: [
      'Data assessment first: volume, quality, transformation rules, dependencies',
      'Use Data Loader or Bulk API 2.0 for large volumes',
      'External IDs on all migrated records for idempotent upserts',
      'Migrate in dependency order: Accounts → Contacts → Opportunities → related records',
      'Disable triggers, validation rules, and workflows during migration (Custom Metadata toggle)',
      'Dry run in full sandbox before production migration',
      'Post-migration reconciliation: record counts, key field spot checks',
      'Keep the source system in read-only mode during cutover',
    ],
    tip: "Show you understand idempotency — migrations fail partway through; External IDs let you re-run safely.",
    answer: `<h4>Opening</h4><p>Data migrations fail when treated as one-shot events. The key is making them <strong>repeatable and verifiable</strong> — run it 10 times, get the same result.</p><h4>Pre-Migration</h4><ul><li>Source data audit: identify duplicates, nulls, invalid formats before you start</li><li>Data mapping document: source field → target field + transformation rules (signed off by business)</li><li>External ID strategy: every migrated record gets an External ID from the source system</li></ul><h4>Execution</h4><ul><li>Disable automation (triggers, flows, validation rules) via Custom Metadata feature flags during load</li><li>Load parent objects before children — respect lookup and master-detail dependencies</li><li>Use upsert with External ID — idempotent and re-runnable without creating duplicates</li></ul><h4>Post-Migration</h4><ul><li>Record count reconciliation: source vs target for every object loaded</li><li>Spot-check critical records manually with the business</li><li>Re-enable automation and monitor for issues in the first 48 hours</li></ul>`
  },
];

const CATEGORIES = ['All','Security','Team Lead','LWC & UI','Data'];

const NAMING_DATA = {
  apex: [
    { type:'Apex Class', cap:'PascalCase', convention:'<Namespace>_<ClassName><OptionalSuffix>', example:'SBCPT_CustomerAssessmentController' },
    { type:'Apex Test Class', cap:'PascalCase', convention:'<ClassBeingTested>_Test', example:'SBCPT_CustomerAssessmentController_Test' },
    { type:'Apex Trigger', cap:'PascalCase', convention:'<ObjectName>Trigger', example:'AccountTrigger' },
    { type:'Apex Trigger Handler', cap:'PascalCase', convention:'<ObjectName>TriggerHandler', example:'AccountTriggerHandler' },
    { type:'Apex Batch Class', cap:'PascalCase', convention:'Batch<Description>', example:'BatchCleanupStaleOpportunities' },
    { type:'Apex Queueable Class', cap:'PascalCase', convention:'<Description>Queueable', example:'SendWelcomeEmailQueueable' },
    { type:'Apex Schedulable Class', cap:'PascalCase', convention:'<Description>Scheduler', example:'NightlyDataCleanupScheduler' },
    { type:'Apex Interface', cap:'PascalCase', convention:'I<InterfaceName>', example:'IPaymentProcessor' },
    { type:'Apex Abstract Class', cap:'PascalCase', convention:'Abstract<ClassName>', example:'AbstractEmailService' },
    { type:'Apex Exception Class', cap:'PascalCase', convention:'<Domain>Exception', example:'PaymentException' },
    { type:'Test Data Factory', cap:'PascalCase', convention:'<Object>TestFactory or TestDataFactory', example:'AccountTestFactory' },
    { type:'Apex Mock / Stub Class', cap:'PascalCase', convention:'Mock<ClassName>', example:'MockCalloutService' },
    { type:'Apex Service Class', cap:'PascalCase', convention:'<Domain>Service', example:'OpportunityService' },
    { type:'Apex Selector Class', cap:'PascalCase', convention:'<Object>Selector', example:'AccountSelector' },
    { type:'Apex Domain Class (fflib)', cap:'PascalCase', convention:'<Object>s (plural)', example:'Accounts' },
    { type:'Apex Methods', cap:'camelCase', convention:'<Verb(s)><OptionalNounSet>', example:'getParentAccount()' },
    { type:'Apex Future Method', cap:'camelCase', convention:'<verb><Description>Async', example:'sendNotificationAsync' },
    { type:'Apex Variables', cap:'camelCase', convention:'<shortMeaningfulNoun>', example:'parentAccount' },
    { type:'Apex Constants', cap:'SNAKE_CASE', convention:'<CAPITALIZED_WORDS>', example:'MAX_CHARACTERS' },
    { type:'Apex Properties', cap:'camelCase', convention:'<nounOrAdjective>', example:'isActive' },
  ],
  objects: [
    { type:'Custom Object', cap:'PascalCase', convention:'<ObjectName>__c', example:'ServiceRequest__c' },
    { type:'Custom Field', cap:'PascalCase', convention:'<FieldName>__c', example:'CountryCode__c' },
    { type:'Custom Metadata Type', cap:'PascalCase', convention:'<Name>__mdt', example:'FeatureFlag__mdt' },
    { type:'Custom Setting (Hierarchy)', cap:'PascalCase', convention:'<Name>_Settings__c', example:'IntegrationSettings__c' },
    { type:'Custom Setting (List)', cap:'PascalCase', convention:'<Name>_Settings__c', example:'TaxRateSettings__c' },
    { type:'Record Type', cap:'PascalCase', convention:'<Adjective><Category> (no spaces)', example:'PremiumAccount, SupportCase' },
    { type:'Page Layout', cap:'Natural Text', convention:'<Object> <RecordType> Layout', example:'Account Premium Layout' },
    { type:'Compact Layout', cap:'Natural Text', convention:'<Object> Compact <Variant>', example:'Opportunity Compact Default' },
    { type:'Validation Rule', cap:'Natural Text', convention:'<Field> <Rule> <OptionalDependency>', example:'Street Address < 60 chars' },
    { type:'Global Value Set (Picklist)', cap:'PascalCase', convention:'<Domain>_<FieldName>Values', example:'Case_StatusValues' },
    { type:'External ID Field', cap:'PascalCase', convention:'<Source>_Id__c', example:'SAP_Id__c, Legacy_Id__c' },
    { type:'Custom Index', cap:'N/A', convention:'Requested via Salesforce Support', example:'Contact.ExternalId__c' },
    { type:'Junction Object', cap:'PascalCase', convention:'<Parent1><Parent2>__c', example:'AccountContact__c' },
    { type:'Big Object', cap:'PascalCase', convention:'<Name>Archive__b', example:'OrderLineArchive__b' },
  ],
  ui: [
    { type:'Lightning Web Component (folder)', cap:'camelCase', convention:'<namespace><ComponentName>', example:'accountLookupCmp' },
    { type:'LWC — HTML Template', cap:'camelCase', convention:'Same as component folder', example:'accountLookupCmp.html' },
    { type:'LWC — JS Controller', cap:'camelCase', convention:'Same as component folder', example:'accountLookupCmp.js' },
    { type:'LWC — CSS Module', cap:'camelCase', convention:'Same as component folder', example:'accountLookupCmp.css' },
    { type:'Aura Component', cap:'PascalCase', convention:'<Namespace>_<ComponentName>Cmp', example:'AccountLookupCmp' },
    { type:'Aura Event', cap:'PascalCase', convention:'<Namespace>_<ComponentName>Evt', example:'AccountSelectedEvt' },
    { type:'Visualforce Page', cap:'PascalCase', convention:'<Namespace>_<PageName>', example:'SBCPT_BundleConfigurations' },
    { type:'Visualforce Component', cap:'PascalCase', convention:'<Namespace>_<ComponentName>Cmp', example:'SBCPT_HeaderCmp' },
    { type:'Lightning App Page', cap:'Natural Text', convention:'<Purpose> Page', example:'Account Management Page' },
    { type:'Lightning Record Page', cap:'Natural Text', convention:'<Object> Record Page <Variant>', example:'Opportunity Record Page Default' },
    { type:'Lightning App', cap:'PascalCase', convention:'<Namespace>_<AppName>App', example:'AccountManagementApp' },
    { type:'Custom Tab', cap:'Natural Text', convention:'<Object or Feature Name>', example:'Service Requests' },
    { type:'Static Resource', cap:'PascalCase', convention:'<Namespace>_<Name>', example:'SBCPT_ChartLibrary' },
    { type:'Experience Cloud Site', cap:'Natural Text', convention:'<Brand/Purpose> Portal', example:'Customer Self-Service Portal' },
    { type:'Lightning Message Channel', cap:'PascalCase', convention:'<Purpose>__c (messageChannel)', example:'RecordSelected__c' },
    { type:'Omniscript', cap:'PascalCase', convention:'<Object>_<Purpose>', example:'Case_CreateWithEscalation' },
  ],
  automations: [
    { type:'Flow — Before-Save Triggered', cap:'Natural Text', convention:'<Object> Before Handler', example:'Case Before Handler' },
    { type:'Flow — After-Save Triggered', cap:'Natural Text', convention:'<Object> After Handler', example:'Case After Handler' },
    { type:'Flow — Scheduled', cap:'Natural Text', convention:'<Short Process Description>', example:'Remind Opportunity Owners' },
    { type:'Flow — Screen Flow', cap:'Natural Text', convention:'<Short Yet Meaningful Description>', example:'Reschedule Order Delivery' },
    { type:'Flow — Autolaunched', cap:'Natural Text', convention:'<Trigger or Purpose> Flow', example:'Send Contract Renewal Flow' },
    { type:'Flow — Platform Event Triggered', cap:'Natural Text', convention:'<EventName> Handler', example:'Order Created Handler' },
    { type:'Flow — Orchestration', cap:'Natural Text', convention:'<Object> <ProcessName> Orchestration', example:'Onboarding Case Orchestration' },
    { type:'Flow Element — Get Records', cap:'Natural Text', convention:'Get <Adj> <Object>', example:'Get Related Contacts' },
    { type:'Flow Element — Create Records', cap:'Natural Text', convention:'Create <Object>', example:'Create Case Comment' },
    { type:'Flow Element — Update Records', cap:'Natural Text', convention:'Update <Object>', example:'Update Opportunity Stage' },
    { type:'Flow Element — Delete Records', cap:'Natural Text', convention:'Delete <Object>', example:'Delete Stale Draft Records' },
    { type:'Flow Element — Screen', cap:'Natural Text', convention:'<Verb> <Short Description>', example:'Collect Contact Details' },
    { type:'Flow Element — Subflow', cap:'Natural Text', convention:'<Label of referenced Flow>', example:'Get Record Type ID' },
    { type:'Flow Element — Action', cap:'Natural Text', convention:'<Brief description of Action>', example:'Send Email to Opportunity Owner' },
    { type:'Flow Element — Assignment', cap:'Natural Text', convention:'Set <Variable> to <Value>', example:'Set Discount to 10%' },
    { type:'Flow Element — Decision', cap:'Natural Text', convention:'<Question>?', example:'Update or Create Contact?' },
    { type:'Flow Element — Decision Outcome', cap:'Natural Text', convention:'<Answer>', example:'Update Existing Contact' },
    { type:'Flow Element — Loop', cap:'Natural Text', convention:'Loop Through <Collection>', example:'Loop Through Child Contacts' },
    { type:'Flow Variable', cap:'camelCase', convention:'var<Description>', example:'varAccountId' },
    { type:'Flow Collection Variable', cap:'camelCase', convention:'col<ObjectName>', example:'colContacts' },
    { type:'Flow Record Variable', cap:'camelCase', convention:'rec<ObjectName>', example:'recOpportunity' },
    { type:'Flow Constant', cap:'camelCase', convention:'const<Name>', example:'constMaxRetries' },
    { type:'Flow Formula', cap:'camelCase', convention:'formula<Description>', example:'formulaFullName' },
    { type:'Process Builder', cap:'Natural Text', convention:'<Object> Handler', example:'Case Handler' },
    { type:'Workflow Rule', cap:'Natural Text', convention:'<Namespace>_<Event that fired>', example:'Date of Birth Changed' },
    { type:'Field Update (Workflow)', cap:'Natural Text', convention:'Set <Field> to <Value>', example:'Set City to Tel Aviv' },
    { type:'Email Alert', cap:'Natural Text', convention:'<Recipient> <Event> Alert', example:'Owner Case Escalation Alert' },
    { type:'Approval Process', cap:'Natural Text', convention:'<Condition that fires the process>', example:'Submit Assessment Record' },
    { type:'Approval Process Step', cap:'Natural Text', convention:'<Outcome> — <Short Description>', example:'Approval — Sent to Manager' },
    { type:'Assignment Rule', cap:'Natural Text', convention:'<Object> <Routing Logic>', example:'Case Round Robin Assignment' },
  ],
  other: [
    { type:'Platform Event', cap:'PascalCase', convention:'<Action><Entity>Event__e', example:'NewOrderEvent__e' },
    { type:'Change Data Capture Event', cap:'PascalCase', convention:'<Object>ChangeEvent', example:'AccountChangeEvent' },
    { type:'Permission Set', cap:'PascalCase', convention:'<Feature>_<AccessLevel>_PS', example:'OpportunityManagement_Edit_PS' },
    { type:'Permission Set Group', cap:'PascalCase', convention:'<Persona>_PSG', example:'SalesRepresentative_PSG' },
    { type:'Named Credential', cap:'PascalCase', convention:'<ServiceName>_<Env>', example:'PaymentGateway_Prod' },
    { type:'External Credential', cap:'PascalCase', convention:'<ServiceName>_ExtCred', example:'Stripe_ExtCred' },
    { type:'Auth Provider', cap:'Natural Text', convention:'<Service> <Type>', example:'Salesforce OIDC' },
    { type:'Remote Site Setting', cap:'PascalCase', convention:'<ServiceName>_<Env>', example:'HerokuApp_Prod' },
    { type:'Connected App', cap:'Natural Text', convention:'<Integration Name> <Purpose>', example:'Mobile App OAuth' },
    { type:'Custom Label', cap:'SNAKE_CASE', convention:'<NAMESPACE>_<LABEL_NAME>', example:'ERROR_ACCOUNT_NOT_FOUND' },
    { type:'Custom Permission', cap:'PascalCase', convention:'<Feature>_<Action>Permission', example:'BulkDelete_Permission' },
    { type:'Muting Permission Set', cap:'PascalCase', convention:'Mute_<Feature>_PS', example:'Mute_BulkDelete_PS' },
    { type:'Report', cap:'Natural Text', convention:'<Business Area> — <Subject> — <Time Frame>', example:'Sales — Open Opportunities — Q3' },
    { type:'Report Type', cap:'Natural Text', convention:'<Primary Object> with <Related Object>', example:'Accounts with Contacts' },
    { type:'Dashboard', cap:'Natural Text', convention:'<Team/Persona> <Purpose> Dashboard', example:'Sales Manager Pipeline Dashboard' },
    { type:'Email Template', cap:'Natural Text', convention:'<Object> <Event> Template', example:'Case Escalation Template' },
    { type:'Letterhead', cap:'Natural Text', convention:'<Brand> <Purpose> Letterhead', example:'Corporate Default Letterhead' },
    { type:'Document / Content', cap:'Natural Text', convention:'<Type> — <Description> — <Version>', example:'Contract — NDA Standard — v2' },
    { type:'Integration / API User', cap:'Natural Text', convention:'<System> Integration User', example:'SAP Integration User' },
    { type:'Certificate', cap:'PascalCase', convention:'<Service>_<Env>_Cert', example:'Heroku_Prod_Cert' },
    { type:'Scratch Org Definition', cap:'camelCase', convention:'<purpose>-scratch-def.json', example:'full-sandbox-scratch-def.json' },
  ]
};

const NAMING_TABS = [
  { id:'apex', label:'Apex' },
  { id:'objects', label:'Objects & Fields' },
  { id:'ui', label:'UI Components' },
  { id:'automations', label:'Automations' },
  { id:'other', label:'Other' },
];

const BEST_PRACTICES = [
  { num:1, title:'One Trigger Per Object', desc:'Avoid multiple triggers on the same object to prevent unexpected execution order and behavior. Use a single trigger that delegates to a handler class.', code:null },
  { num:2, title:'Use Trigger Context Variables Wisely', desc:'Use Trigger.isInsert, Trigger.isUpdate, Trigger.new, Trigger.oldMap etc. Handle logic correctly per DML event and timing.', code:`if (Trigger.isInsert && Trigger.isBefore) {\n  handler.onBeforeInsert(Trigger.new);\n}` },
  { num:3, title:'Bulkify Your Code', desc:'Never write SOQL or DML inside loops. Always design for 200 records. Use collections, maps, and sets for efficient batch processing.', code:`// ❌ Bad\nfor (Account a : Trigger.new) {\n  List<Contact> c = [SELECT Id FROM Contact\n    WHERE AccountId = :a.Id];\n}\n\n// ✅ Good\nSet<Id> ids = Trigger.newMap.keySet();\nList<Contact> contacts = [SELECT Id\n  FROM Contact WHERE AccountId IN :ids];` },
  { num:4, title:'Use a Trigger Handler Class', desc:'Move all logic into a dedicated handler class. Triggers should be thin — just call the handler. Makes code modular, testable, and easy to debug.', code:`trigger AccountTrigger on Account\n    (before insert, after update) {\n  AccountTriggerHandler.handle(\n    Trigger.operationType\n  );\n}` },
  { num:5, title:'Keep Business Logic Out of Triggers', desc:'Let the handler or a service layer handle validations, DML, and orchestration. Triggers should only route, never decide.', code:null },
  { num:6, title:'Use Static Variables to Avoid Recursion', desc:'Prevent infinite loops during nested updates using a static boolean flag in your handler class. Reset only when intentional re-entry is needed.', code:`public class AccountTriggerHandler {\n  private static Boolean hasRun = false;\n  public static void handle() {\n    if (hasRun) return;\n    hasRun = true;\n    // logic here\n  }\n}` },
  { num:7, title:'Handle All Trigger Contexts', desc:'Handle all relevant DML events: before insert, before update, after insert, after update, before delete, after delete, after undelete. Don\'t leave gaps.', code:null },
  { num:8, title:'Respect Security (CRUD, FLS, Sharing)', desc:'Always enforce field-level and object-level security in Apex. Use stripInaccessible() for FLS and with sharing on every class unless explicitly justified.', code:`SObjectAccessDecision d =\n  Security.stripInaccessible(\n    AccessType.READABLE, results\n  );\nList<Account> safe = d.getRecords();` },
  { num:9, title:'Write Unit Tests for Each Context', desc:'Test bulk scenarios (200 records), recursion prevention, negative paths, and each trigger context. Aim for 80%+ meaningful coverage — not just line-hit coverage.', code:null },
  { num:10, title:'Avoid Hardcoded IDs', desc:'Never embed record IDs or org-specific values in Apex. Use SOQL queries, Custom Metadata, Custom Labels, or Custom Settings instead.', code:`// ❌ Bad\nif (acct.RecordTypeId == '012XXXXXX') {}\n\n// ✅ Good\nId rtId = Schema.SObjectType.Account\n  .getRecordTypeInfosByDeveloperName()\n  .get('Premium').getRecordTypeId();` },
  { num:11, title:'Use the Limits Class for Defensive Programming', desc:'Check governor limit consumption at runtime using the Limits class. Use it to degrade gracefully, log, or break processing before hitting hard limits.', code:`System.debug('SOQL used: '\n  + Limits.getQueries());\nSystem.debug('DML used: '\n  + Limits.getDmlStatements());\nif (Limits.getQueries() >=\n    Limits.getLimitQueries() - 5) {\n  // gracefully defer or log\n}` },
];

const GOV_LIMITS = {
  apexCode: [
    { desc:'Total stack depth (recursive triggers)', sync:'16', async:'16', hl:false },
    { desc:'Total heap size', sync:'6 MB', async:'12 MB', hl:true },
    { desc:'Maximum CPU time on Salesforce servers', sync:'10,000 ms', async:'60,000 ms', hl:true },
    { desc:'Maximum execution time per transaction', sync:'10 min', async:'10 min', hl:false },
    { desc:'Apex trigger batch size', sync:'200', async:'200', hl:true },
    { desc:'For loop list batch size', sync:'200', async:'200', hl:true },
    { desc:'Max class/trigger code units in a deployment', sync:'7,500', async:'7,500', hl:false },
  ],
  callouts: [
    { desc:'Total callouts (HTTP / web services) per transaction', sync:'100', async:'100', hl:true },
    { desc:'Maximum cumulative callout timeout', sync:'120 sec', async:'120 sec', hl:true },
    { desc:'Default timeout per callout', sync:'10 sec', async:'10 sec', hl:false },
    { desc:'Maximum callout request or response size', sync:'6 MB', async:'12 MB', hl:false },
    { desc:'Max EventBus.publish calls (publish-immediately events)', sync:'150', async:'150', hl:false },
    { desc:'Max push notification method calls per transaction', sync:'10', async:'10', hl:false },
    { desc:'Max push notifications per method call', sync:'2,000', async:'2,000', hl:false },
    { desc:'Total sendEmail methods allowed', sync:'10', async:'10', hl:false },
    { desc:'Max Apex classes scheduled concurrently', sync:'100', async:'100', hl:false },
  ],
  queries: [
    { desc:'Total SOQL queries issued', sync:'100', async:'200', hl:true },
    { desc:'Total records retrieved by SOQL queries', sync:'50,000', async:'50,000', hl:true },
    { desc:'Max SOQL query run time before cancellation', sync:'120 sec', async:'120 sec', hl:false },
    { desc:'Records retrieved by Database.getQueryLocator', sync:'10,000', async:'10,000', hl:false },
    { desc:'Max records in Batch Apex Database.QueryLocator', sync:'50 million', async:'50 million', hl:true },
    { desc:'Total SOSL queries issued', sync:'20', async:'20', hl:false },
    { desc:'Total records retrieved by a single SOSL query', sync:'2,000', async:'2,000', hl:false },
    { desc:'Max Apex cursor rows per cursor', sync:'50 million', async:'50 million', hl:false },
    { desc:'Max Apex cursors per day (org)', sync:'10,000', async:'10,000', hl:false },
    { desc:'Max cursor fetch calls per transaction', sync:'10', async:'10', hl:false },
    { desc:'Max Apex cursor rows fetched per day (aggregate)', sync:'100 million', async:'100 million', hl:false },
  ],
  dml: [
    { desc:'Total DML statements issued', sync:'150', async:'150', hl:true },
    { desc:'Total records processed by DML / Approval.process / emptyRecycleBin', sync:'10,000', async:'10,000', hl:true },
  ],
  async: [
    { desc:'Max @future methods per Apex invocation', sync:'50', async:'0 (batch/future); 50 (queueable)', hl:true },
    { desc:'Max System.enqueueJob calls per transaction', sync:'50', async:'1', hl:true },
    { desc:'Max batch Apex jobs in Holding status (flex queue)', sync:'100', async:'100', hl:false },
    { desc:'Max batch Apex jobs queued or active concurrently', sync:'5', async:'5', hl:true },
    { desc:'Max batch Apex start() concurrent executions', sync:'1', async:'1', hl:false },
    { desc:'Max batch jobs submitted in a running test', sync:'5', async:'5', hl:false },
  ],
};

const ASYNC_MATRIX = [
  { caller:'Future',         future:'❌ Not Allowed',    queueable:'✅ Allowed',         batch:'❌ Not Allowed' },
  { caller:'Queueable',      future:'✅ Allowed (Max 50)', queueable:'✅ Allowed (Max 1)', batch:'✅ Allowed' },
  { caller:'Batch — start()', future:'❌ Not Allowed',   queueable:'✅ Allowed (Max 1)', batch:'❌ Not Allowed' },
  { caller:'Batch — execute()', future:'❌ Not Allowed', queueable:'✅ Allowed (Max 1)', batch:'❌ Not Allowed' },
  { caller:'Batch — finish()', future:'❌ Not Allowed',  queueable:'✅ Allowed (Max 1)', batch:'✅ Allowed (no max)' },
];

const GOV_TABS = [
  { id:'apexCode', label:'Apex Code' },
  { id:'callouts', label:'Callouts & Events' },
  { id:'queries', label:'Queries (SOQL/SOSL)' },
  { id:'dml', label:'DML' },
  { id:'async', label:'Async Apex' },
];

// ───────────────────────────────────────────────
// COMPONENTS
// ───────────────────────────────────────────────

function PriorityBadge({ p }) {
  const cls = p === 'Must know' ? 'badge-must' : p === 'Important' ? 'badge-important' : 'badge-good';
  return <span className={`badge ${cls}`}>{p}</span>;
}

function Modal({ topic, onClose }) {
  useEffect(() => {
    const fn = e => e.key === 'Escape' && onClose();
    document.addEventListener('keydown', fn);
    return () => document.removeEventListener('keydown', fn);
  }, []);
  return (
    <div className="modal-overlay" onClick={e => e.target === e.currentTarget && onClose()}>
      <div className="modal">
        <button className="modal-close" onClick={onClose}>✕</button>
        <div className="modal-label">Practice Question & Model Answer</div>
        <div className="modal-q">{topic.title}</div>
        <div className="modal-body" dangerouslySetInnerHTML={{ __html: topic.answer }} />
      </div>
    </div>
  );
}

function InterviewCard({ topic, onPractice, onToggle }) {
  return (
    <div className={`interview-card${topic.reviewed ? ' reviewed' : ''}`}>
      <div className="card-header">
        <div className="card-badges">
          <PriorityBadge p={topic.priority} />
          <span className="badge badge-cat">{topic.category}</span>
        </div>
        <div className={`review-check${topic.reviewed ? ' checked' : ''}`} onClick={() => onToggle(topic.id)} title="Toggle reviewed">
          {topic.reviewed ? '✓' : ''}
        </div>
      </div>
      <div className="card-title">{topic.title}</div>
      <ul className="card-points">
        {topic.points.map((p, i) => <li key={i}>{p}</li>)}
      </ul>
      <div className="card-tip"><strong>💡 Interview tip:</strong> {topic.tip}</div>
      <div className="card-actions">
        <button className="btn btn-primary" onClick={() => onPractice(topic)}>Practice this ↗</button>
        <button className={`btn ${topic.reviewed ? 'btn-success' : 'btn-secondary'}`} onClick={() => onToggle(topic.id)}>
          {topic.reviewed ? '✓ Reviewed' : 'Mark reviewed'}
        </button>
      </div>
    </div>
  );
}

function InterviewSection({ topics, setTopics }) {
  const [filter, setFilter] = useState('All');
  const [modal, setModal] = useState(null);
  const filtered = filter === 'All' ? topics : topics.filter(t => t.category === filter);
  const reviewed = topics.filter(t => t.reviewed).length;
  const toggle = id => setTopics(prev => prev.map(t => t.id === id ? {...t, reviewed: !t.reviewed} : t));
  return (
    <section className="section" id="interview">
      <div className="section-header">
        <span className="section-label">// 01 — Interview Prep</span>
        <div className="section-title">Comprehensive Topic Guide</div>
        <div className="section-desc">Click "Practice this" on any card to reveal a model answer. Mark topics reviewed to track your progress.</div>
      </div>
      <div className="filters">
        {CATEGORIES.map(c => (
          <button key={c} className={`filter-btn${filter === c ? ' active' : ''}`} onClick={() => setFilter(c)}>{c}</button>
        ))}
        <span className="filter-count">{reviewed}/{topics.length} reviewed</span>
      </div>
      <div className="cards-grid">
        {filtered.map(t => <InterviewCard key={t.id} topic={t} onPractice={setModal} onToggle={toggle} />)}
      </div>
      {modal && <Modal topic={modal} onClose={() => setModal(null)} />}
    </section>
  );
}

function NamingSection() {
  const [tab, setTab] = useState('apex');
  const data = NAMING_DATA[tab];
  return (
    <section className="section" id="naming">
      <div className="section-header">
        <span className="section-label">// 02 — Naming Conventions</span>
        <div className="section-title">Naming Standards Reference</div>
        <div className="section-desc">Team-wide naming standards with extended coverage across all Salesforce artifact types.</div>
      </div>
      <div className="tabs">
        {NAMING_TABS.map(t => (
          <button key={t.id} className={`tab-btn${tab === t.id ? ' active' : ''}`} onClick={() => setTab(t.id)}>{t.label} <span style={{color:'var(--text-dim)',fontSize:'11px'}}>({NAMING_DATA[t.id].length})</span></button>
        ))}
      </div>
      <div className="table-wrap">
        <table>
          <thead><tr><th>Type</th><th>Capitalization</th><th>Convention</th><th>Example</th></tr></thead>
          <tbody>
            {data.map((row, i) => (
              <tr key={i}>
                <td className="td-type">{row.type}</td>
                <td className="td-cap">{row.cap}</td>
                <td className="td-convention">{row.convention}</td>
                <td className="td-example">{row.example}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </section>
  );
}

function BestPracticesSection() {
  return (
    <section className="section" id="practices">
      <div className="section-header">
        <span className="section-label">// 03 — Best Practices</span>
        <div className="section-title">Apex Trigger Best Practices</div>
        <div className="section-desc">11 rules for production-grade Apex trigger code with code examples.</div>
      </div>
      <div className="practices-grid">
        {BEST_PRACTICES.map(p => (
          <div key={p.num} className="practice-card">
            <div className="practice-num">{String(p.num).padStart(2,'0')}</div>
            <div>
              <div className="practice-title">{p.title}</div>
              <div className="practice-desc">{p.desc}</div>
              {p.code && <pre className="practice-code">{p.code}</pre>}
            </div>
          </div>
        ))}
      </div>
    </section>
  );
}

function GovernorLimitsSection() {
  const [tab, setTab] = useState('apexCode');
  const data = GOV_LIMITS[tab];
  return (
    <section className="section" id="limits">
      <div className="section-header">
        <span className="section-label">// 04 — Governor Limits</span>
        <div className="section-title">Salesforce Governor Limits</div>
        <div className="section-desc">Key limits for synchronous and asynchronous Apex contexts. ★ starred rows are the ones you must know cold.</div>
      </div>
      <div className="tabs">
        {GOV_TABS.map(t => (
          <button key={t.id} className={`tab-btn${tab === t.id ? ' active' : ''}`} onClick={() => setTab(t.id)}>{t.label}</button>
        ))}
      </div>
      {tab === 'async' && (
        <div style={{marginBottom:'24px'}}>
          <div style={{fontSize:'12px',color:'var(--text-muted)',fontFamily:"'JetBrains Mono',monospace",marginBottom:'12px',letterSpacing:'0.5px'}}>// Async Process Calling Behaviour Matrix</div>
          <div className="table-wrap" style={{marginBottom:'16px'}}>
            <table>
              <thead><tr><th>Calling Context</th><th>Can call Future?</th><th>Can call Queueable?</th><th>Can call Batch?</th></tr></thead>
              <tbody>
                {ASYNC_MATRIX.map((r, i) => (
                  <tr key={i}>
                    <td className="td-type">{r.caller}</td>
                    <td className={r.future.includes('❌') ? 'cell-no' : 'cell-yes'}>{r.future}</td>
                    <td className={r.queueable.includes('❌') ? 'cell-no' : 'cell-yes'}>{r.queueable}</td>
                    <td className={r.batch.includes('❌') ? 'cell-no' : 'cell-yes'}>{r.batch}</td>
                  </tr>
                ))}
              </tbody>
            </table>
          </div>
          <div className="async-note">
            <strong>Queueable chaining:</strong> You can chain jobs indefinitely, but only <strong>one child per parent job</strong>. Developer Edition orgs are limited to a chain depth of 5 (max 5 jobs including the initial parent). Multiple child jobs from the same parent are <strong>not supported</strong>.
          </div>
        </div>
      )}
      <div className="table-wrap">
        <table>
          <thead><tr><th>Description</th><th>Sync Limit</th><th>Async Limit</th></tr></thead>
          <tbody>
            {data.map((row, i) => (
              <tr key={i} className={row.hl ? 'limit-highlight' : ''}>
                <td>{row.desc}</td>
                <td className="limit-sync">{row.sync}</td>
                <td className="limit-async">{row.async}</td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
      {tab === 'apexCode' && (
        <div className="limit-callout">
          <div className="limit-callout-item">
            <div className="lc-title" style={{color:'var(--blue)'}}>Sync → Async upgrade</div>
            <div style={{color:'var(--text-muted)',fontSize:'13px'}}>Heap doubles (6→12 MB) and CPU increases 6× (10s→60s) when moving to async</div>
          </div>
          <div className="limit-callout-item">
            <div className="lc-title" style={{color:'var(--green)'}}>Trigger batch size</div>
            <div style={{color:'var(--text-muted)',fontSize:'13px'}}>Always design for 200 records. Never write code that assumes a single record</div>
          </div>
          <div className="limit-callout-item">
            <div className="lc-title" style={{color:'var(--orange)'}}>Deployment limit</div>
            <div style={{color:'var(--text-muted)',fontSize:'13px'}}>7,500 code units includes classes, triggers, and pages — keep dead code pruned</div>
          </div>
        </div>
      )}
      {tab === 'queries' && (
        <div className="limit-callout">
          <div className="limit-callout-item">
            <div className="lc-title" style={{color:'var(--blue)'}}>Selectivity rule</div>
            <div style={{color:'var(--text-muted)',fontSize:'13px'}}>A query is selective when WHERE filters return &lt; 10% of records or &lt; 333K (whichever is smaller)</div>
          </div>
          <div className="limit-callout-item">
            <div className="lc-title" style={{color:'var(--green)'}}>Async SOQL boost</div>
            <div style={{color:'var(--text-muted)',fontSize:'13px'}}>Async contexts double the SOQL query count (100 → 200). Use this for complex integrations</div>
          </div>
        </div>
      )}
    </section>
  );
}

function Navbar({ reviewedCount, total, scrollTo }) {
  return (
    <nav className="nav">
      <div className="nav-inner">
        <span className="nav-logo" onClick={() => window.scrollTo({top:0,behavior:'smooth'})}>
          SF<span> Lead Guide</span>
        </span>
        <div className="nav-links">
          {[['interview','Interview Prep'],['naming','Naming Conventions'],['practices','Best Practices'],['limits','Governor Limits']].map(([id, label]) => (
            <button key={id} className="nav-link" onClick={() => scrollTo(id)}>{label}</button>
          ))}
        </div>
        <div className="nav-progress"><strong>{reviewedCount}</strong>/{total} reviewed</div>
      </div>
    </nav>
  );
}

function App() {
  const [topics, setTopics] = useState(INTERVIEW_DATA);
  const reviewed = topics.filter(t => t.reviewed).length;
  const scrollTo = id => document.getElementById(id)?.scrollIntoView({ behavior:'smooth', block:'start' });
  return (
    <>
      <Navbar reviewedCount={reviewed} total={topics.length} scrollTo={scrollTo} />
      <main>
        <div className="hero">
          <div className="hero-glow" />
          <div className="hero-glow2" />
          <div className="hero-eyebrow">Salesforce Team Lead Interview Guide</div>
          <h1>Nail Every<br/><span className="accent">Round.</span></h1>
          <p className="hero-desc">A comprehensive interactive reference covering interview topics, naming conventions, Apex best practices, and governor limits. Filter, practice, and track your progress.</p>
          <div className="hero-stats">
            <div><div className="stat-num">9</div><div className="stat-label">Interview Topics</div></div>
            <div><div className="stat-num">95+</div><div className="stat-label">Naming Rules</div></div>
            <div><div className="stat-num">11</div><div className="stat-label">Best Practices</div></div>
            <div><div className="stat-num">40+</div><div className="stat-label">Governor Limits</div></div>
          </div>
        </div>
        <InterviewSection topics={topics} setTopics={setTopics} />
        <NamingSection />
        <BestPracticesSection />
        <GovernorLimitsSection />
      </main>
      <footer className="footer">
        Built for <span>Salesforce Team Leads</span> · Study hard, ship clean code, lead great teams 🚀
      </footer>
    </>
  );
}

ReactDOM.createRoot(document.getElementById('root')).render(<App />);
</script>
</body>
</html>
