
<h1 align="center">🇵🇰 PakVista</h1>

<p align="center">
  <strong>Containerized Static Web Application with Production-Grade CI/CD</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx">
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Render-000000?style=for-the-badge&logo=render&logoColor=white" alt="Render">
</p>

---

<h2>📌 Project Overview</h2>

<p>
  <strong>PakVista</strong> is a containerized static web application designed to showcase
  Pakistan's top five tourist destinations.
</p>

<p>
  The primary focus of this project is the implementation of a complete,
  production-grade <strong>Continuous Integration and Continuous Deployment (CI/CD)</strong>
  pipeline across three isolated software environments:
  <strong>Development</strong>, <strong>Staging</strong>, and <strong>Production</strong>.
</p>

<p>
  The application strictly utilizes <strong>HTML5 and CSS3</strong> without JavaScript,
  while the infrastructure follows a professional GitFlow-based development lifecycle
  with automated testing, containerization, image publishing, and deployment.
</p>

---

<h2>🎯 Project Objectives</h2>

<ul>
  <li>Build a responsive static tourism website using HTML5 and CSS3.</li>
  <li>Containerize the application using Docker and Nginx.</li>
  <li>Implement a professional GitFlow branching strategy.</li>
  <li>Maintain isolated Development, Staging, and Production environments.</li>
  <li>Automate CI using GitHub Actions.</li>
  <li>Automate production deployments through Render deploy hooks.</li>
  <li>Apply branch protection and Pull Request approval requirements.</li>
  <li>Publish versioned Docker images to Docker Hub.</li>
</ul>

---

<h2>👨‍💻 My Role — Team Lead</h2>

<p>
  As the <strong>Team Lead</strong> for a five-person engineering team, I was responsible
  for the repository architecture, infrastructure configuration, CI/CD implementation,
  and deployment orchestration.
</p>

<h3>My Contributions</h3>

<ul>
  <li>
    <strong>Repository & Workflow Architecture:</strong>
    Established the three-tier branching strategy
    <code>develop → staging → main</code> and enforced branch protection rules
    requiring approved Pull Requests and passing status checks.
  </li>

  <li>
    <strong>Pipeline Engineering:</strong>
    Authored the Development CI workflow
    <code>ci-dev.yml</code>, including automated linting, building,
    Docker authentication, and image tagging.
  </li>

  <li>
    <strong>Production Deployment:</strong>
    Authored the Production CD workflow
    <code>cd-prod.yml</code> to automate live deployments.
  </li>

  <li>
    <strong>Containerization:</strong>
    Designed the multi-stage <code>Dockerfile</code> using
    <code>nginx:alpine</code> to containerize the static application.
  </li>

  <li>
    <strong>Environment & Security:</strong>
    Configured GitHub Environments and managed encrypted secrets
    for Docker Hub authentication and Render deployment hooks.
  </li>

  <li>
    <strong>Frontend Development:</strong>
    Developed the root <code>index.html</code> landing page and established
    the shared <code>style.css</code> design system used by the team.
  </li>

  <li>
    <strong>Integration & Code Review:</strong>
    Reviewed team Pull Requests, resolved merge conflicts,
    and managed the promotion of code from Development through Production.
  </li>
</ul>

---

<h2>🏗️ System Architecture</h2>

<p>
  PakVista follows a three-environment deployment architecture where code progresses
  through controlled environments before reaching production.
</p>

<table>
  <thead>
    <tr>
      <th>Environment</th>
      <th>Branch</th>
      <th>Purpose</th>
      <th>Deployment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Development</td>
      <td><code>develop</code></td>
      <td>Active development and integration</td>
      <td><code>pakvista-dev</code></td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><code>staging</code></td>
      <td>Pre-release validation</td>
      <td><code>pakvista-staging</code></td>
    </tr>
    <tr>
      <td>Production</td>
      <td><code>main</code></td>
      <td>Live public application</td>
      <td><code>pakvista-prod</code></td>
    </tr>
  </tbody>
</table>

---

<h2>🔄 CI/CD Workflow</h2>

<h3>1. Development</h3>

<ol>
  <li>Developers create feature branches from <code>develop</code>.</li>
  <li>Changes are submitted through Pull Requests.</li>
  <li>GitHub Actions automatically runs the CI pipeline.</li>
  <li>HTML and CSS are linted for code quality.</li>
  <li>The Docker image is built and validated.</li>
  <li>The image is tagged with the environment and commit SHA.</li>
  <li>The image is pushed to Docker Hub.</li>
  <li>The changes are merged into <code>develop</code>.</li>
  <li>The Development environment is deployed on Render.</li>
</ol>

<h3>2. Staging</h3>

<ol>
  <li>Validated changes are promoted from <code>develop</code> to <code>staging</code>.</li>
  <li>CI checks are executed against the staging branch.</li>
  <li>A staging-specific Docker image is created and published.</li>
  <li>The staging environment is updated for pre-release testing.</li>
</ol>

<h3>3. Production</h3>

<ol>
  <li>Approved staging changes are promoted to <code>main</code>.</li>
  <li>Production CI checks are executed.</li>
  <li>The production Docker image is built and published.</li>
  <li>The Production CD workflow is triggered.</li>
  <li>GitHub Actions sends an HTTP POST request using <code>curl</code>.</li>
  <li>The Render production deploy hook triggers a new deployment.</li>
  <li>The updated application becomes available on the live service.</li>
</ol>

---

<h2>🌳 GitFlow Strategy</h2>

<pre>
feature/*
    │
    ▼
 develop
    │
    ▼
 staging
    │
    ▼
  main
    │
    ▼
Production
</pre>

<p>
  The repository uses isolated branches to prevent unfinished development work
  from reaching production prematurely.
</p>

<table>
  <thead>
    <tr>
      <th>Branch</th>
      <th>Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>feature/*</code></td>
      <td>Individual feature development</td>
    </tr>
    <tr>
      <td><code>develop</code></td>
      <td>Development integration</td>
    </tr>
    <tr>
      <td><code>staging</code></td>
      <td>Pre-production validation</td>
    </tr>
    <tr>
      <td><code>main</code></td>
      <td>Production-ready code</td>
    </tr>
  </tbody>
</table>

---

<h2>⚙️ Continuous Integration</h2>

<p>
  The CI pipeline is automatically triggered when Pull Requests target
  the primary environment branches.
</p>

<ul>
  <li>Checkout source code</li>
  <li>Install project dependencies</li>
  <li>Run HTMLHint</li>
  <li>Run Stylelint</li>
  <li>Build the application</li>
  <li>Authenticate with Docker Hub</li>
  <li>Build the Docker image</li>
  <li>Apply environment-specific tags</li>
  <li>Apply commit SHA tags</li>
  <li>Push the image to Docker Hub</li>
</ul>

<h3>Example Image Tags</h3>

<pre>
pakvista:dev-latest
pakvista:&lt;commit-sha&gt;

pakvista:staging-latest
pakvista:&lt;commit-sha&gt;

pakvista:prod-latest
pakvista:&lt;commit-sha&gt;
</pre>

---

<h2>🚀 Continuous Deployment</h2>

<p>
  Production deployment is automated through GitHub Actions and Render deploy hooks.
</p>

<p>
  Once changes are successfully merged into the <code>main</code> branch,
  the Production CD workflow accesses the protected GitHub Environment secrets
  and triggers the Render deployment through an HTTP POST request.
</p>

<pre>
GitHub
   │
   │ Push / Merge
   ▼
main
   │
   ▼
GitHub Actions
   │
   ├── Build Docker Image
   │
   ├── Push to Docker Hub
   │
   └── Trigger Render Deploy Hook
             │
             ▼
       pakvista-prod
</pre>

---

<h2>🐳 Containerization</h2>

<p>
  The application is packaged into a lightweight Docker container using
  <strong>Nginx Alpine</strong>.
</p>

<p>
  A multi-stage Dockerfile is used to separate the build environment
  from the final lightweight production image.
</p>

<pre>
Source Code
     │
     ▼
Docker Build
     │
     ▼
Nginx Alpine Image
     │
     ▼
Docker Hub
     │
     ▼
Render
</pre>

<p>
  Using Nginx Alpine keeps the production container lightweight and
  well-suited for serving static HTML and CSS assets.
</p>

---

<h2>🔐 Environment & Security</h2>

<p>
  Each deployment environment is isolated through GitHub Environments.
  Sensitive credentials are stored using encrypted GitHub Secrets rather than
  being committed to the repository.
</p>

<ul>
  <li>Docker Hub authentication credentials</li>
  <li>Render deployment hooks</li>
  <li>Environment-specific deployment configuration</li>
</ul>

<p>
  Branch protection rules additionally require Pull Request approvals
  and successful CI status checks before changes can be merged.
</p>

---

<h2>🛠️ Tech Stack</h2>

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Technology</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Frontend</td>
      <td>HTML5, CSS3</td>
    </tr>
    <tr>
      <td>Containerization</td>
      <td>Docker</td>
    </tr>
    <tr>
      <td>Web Server</td>
      <td>Nginx Alpine</td>
    </tr>
    <tr>
      <td>Container Registry</td>
      <td>Docker Hub</td>
    </tr>
    <tr>
      <td>CI/CD</td>
      <td>GitHub Actions</td>
    </tr>
    <tr>
      <td>Version Control</td>
      <td>Git & GitFlow</td>
    </tr>
    <tr>
      <td>Hosting</td>
      <td>Render</td>
    </tr>
    <tr>
      <td>HTML Linting</td>
      <td>HTMLHint</td>
    </tr>
    <tr>
      <td>CSS Linting</td>
      <td>Stylelint</td>
    </tr>
    <tr>
      <td>Build Tool</td>
      <td>Parcel</td>
    </tr>
  </tbody>
</table>

---

<h2>📁 Repository Structure</h2>

<pre>
PakVista/
│
├── .github/
│   └── workflows/
│       ├── ci-dev.yml
│       ├── ci-staging.yml
│       ├── ci-prod.yml
│       ├── cd-dev.yml
│       ├── cd-staging.yml
│       └── cd-prod.yml
│
├── src/
│   ├── index.html
│   └── style.css
│
├── Dockerfile
├── package.json
├── .dockerignore
├── .gitignore
└── README.md
</pre>

---

<h2>📊 Deployment Pipeline</h2>

<table>
  <thead>
    <tr>
      <th>Stage</th>
      <th>Git Branch</th>
      <th>CI</th>
      <th>Docker</th>
      <th>Deployment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Development</td>
      <td><code>develop</code></td>
      <td>✅</td>
      <td>🐳</td>
      <td>Render Dev</td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><code>staging</code></td>
      <td>✅</td>
      <td>🐳</td>
      <td>Render Staging</td>
    </tr>
    <tr>
      <td>Production</td>
      <td><code>main</code></td>
      <td>✅</td>
      <td>🐳</td>
      <td>Render Production</td>
    </tr>
  </tbody>
</table>

---

<h2>✨ Key Features</h2>

<ul>
  <li>🇵🇰 Showcase of Pakistan's top five tourist destinations</li>
  <li>📱 Responsive static website</li>
  <li>🐳 Dockerized application</li>
  <li>⚡ Lightweight Nginx Alpine production server</li>
  <li>🔄 Automated CI/CD pipelines</li>
  <li>🌳 GitFlow-based development lifecycle</li>
  <li>🔐 Protected GitHub environments and encrypted secrets</li>
  <li>✅ Automated HTML and CSS quality checks</li>
  <li>🏷️ Environment-specific Docker image tagging</li>
  <li>🚀 Automated Render deployments</li>
</ul>

---

<h2>🎓 Learning Outcomes</h2>

<p>
  This project provided hands-on experience with professional DevOps practices,
  including:
</p>

<ul>
  <li>Designing multi-environment deployment architectures</li>
  <li>Implementing GitFlow branching strategies</li>
  <li>Building CI/CD pipelines with GitHub Actions</li>
  <li>Containerizing static applications with Docker</li>
  <li>Managing Docker images and registries</li>
  <li>Configuring protected deployment environments</li>
  <li>Managing CI/CD secrets securely</li>
  <li>Automating cloud deployments with deployment hooks</li>
  <li>Performing Pull Request reviews and merge management</li>
</ul>

---

<h2>👥 Team</h2>

<p>
  PakVista was developed by a <strong>five-person engineering team</strong>,
  following a collaborative GitFlow-based development and review process.
</p>

<p>
  <strong>My Position:</strong> Team Lead
</p>

---

<h2>📌 Project Summary</h2>

<p>
  PakVista demonstrates how a simple static website can be transformed into
  a professional software delivery workflow through containerization,
  automated quality checks, GitFlow, isolated environments, and automated
  cloud deployment.
</p>

<p align="center">
  <strong>HTML5 + CSS3 → GitFlow → GitHub Actions → Docker → Docker Hub → Render</strong>
</p>
