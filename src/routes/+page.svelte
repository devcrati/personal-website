<script lang="ts">
  import axios from "axios";
  import { onMount } from "svelte";

  let title: string = "Jeremy Jiang";
  let leetcodeStats = {
    easy: { complete: 0, total: 0 },
    medium: { complete: 0, total: 0 },
    hard: { complete: 0, total: 0 },
    total: { complete: 0, total: 0 },
  };

  const socialLinks = [
    {
      href: "https://github.com/devcrati",
      icon: "fa-brands fa-github",
      text: "Github",
    },
    {
      href: "https://stackoverflow.com/users/14888930/crati",
      icon: "fa-brands fa-stack-overflow",
      text: "stack-overflow"
    },
    {
      href: "https://x.com/cratikanon",
      icon: "fa-brands fa-x-twitter",
      text: "X (formerly Twitter)",
    }
  ];

  const techStack = [
  [
    { href: "https://www.python.org/", text: "Python" },
    {
      href: "https://developer.mozilla.org/en-US/docs/Web/JavaScript",
      text: "JavaScript",
    },
    { href: "https://www.typescriptlang.org/", text: "TypeScript" },
    { href: "https://www.ruby-lang.org/en/", text: "Ruby" },
    { href: "https://learn.microsoft.com/en-us/dotnet/csharp/", text: "C#" },
    { href: "https://soliditylang.org/", text: "Solidity" },
    { href: "https://en.wikipedia.org/wiki/SQL", text: "SQL" },
  ],
  [
    { href: "https://nodejs.org/en/", text: "Node.js" },
    { href: "https://nestjs.com/", text: "Nest.js" },
    { href: "https://reactjs.org/", text: "React.js" },
    { href: "https://nextjs.org/", text: "Next.js" },
    { href: "https://reactnative.dev/", text: "React Native" },
    { href: "https://vuejs.org/", text: "Vue" },
    { href: "https://fastapi.tiangolo.com/", text: "FastAPI" },
    { href: "https://expressjs.com/", text: "Express.js" },
    { href: "https://tailwindcss.com/", text: "Tailwind CSS" },
  ],
  [
    { href: "https://spring.io/projects/spring-boot", text: "Spring Boot" },
    { href: "https://learn.microsoft.com/en-us/dotnet/core/", text: ".NET Core" },
    { href: "https://hibernate.org/", text: "Hibernate" },
    { href: "https://www.postgresql.org/", text: "PostgreSQL" },
    { href: "https://www.mongodb.com/", text: "MongoDB" },
    { href: "https://www.prisma.io/", text: "Prisma" },
    { href: "https://typeorm.io/", text: "TypeORM" },
    { href: "https://www.docker.com/", text: "Docker" },
    { href: "https://kubernetes.io/", text: "Kubernetes" },
  ],
  [
    { href: "https://aws.amazon.com/", text: "AWS" },
    { href: "https://azure.microsoft.com/", text: "Azure" },
    { href: "https://cloud.google.com/", text: "GCP" },
    { href: "https://firebase.google.com/", text: "Firebase" },
    { href: "https://supabase.com/", text: "Supabase" },
    { href: "https://swagger.io/", text: "Swagger" },
    { href: "https://www.openapis.org/", text: "OpenAPI" },
    { href: "https://kafka.apache.org/", text: "Kafka" },
    { href: "https://grpc.io/", text: "gRPC" },
  ],
  [
    { href: "https://numpy.org/", text: "NumPy" },
    { href: "https://pandas.pydata.org/", text: "Pandas" },
    { href: "https://scikit-learn.org/", text: "scikit-learn" },
    { href: "https://pytorch.org/", text: "PyTorch" },
    { href: "https://huggingface.co/", text: "Hugging Face" },
    { href: "https://spacy.io/", text: "spaCy" },
    { href: "https://developer.nvidia.com/cuda-toolkit", text: "CUDA" },
  ],
];
</script>

<div id="container--main">
  <section id="wrapper--hero" class="section--page">
    <img
      id="profile-pic"
      src="images/photo.png"
      alt="Jeremy Jiang"
      title="Follow me: @cratikanon on X (formerly Twitter)"
    />

    <div>
      <h1 id="user-name">{title}</h1>
      <p>
        <a
          href="mailto:jeremy.jiang9451@gmail.com"
          target="_blank"
          rel="noopener noreferrer"
          class="email"
        >
          jeremy.jiang9451@gmail.com</a
        >
        •
        <a
          href="mailto:naiv@jeremys.xyz"
          target="_blank"
          rel="noopener noreferrer"
          class="email">naiv@jeremys.xyz</a
        >
      </p>
      <p>
        <a class="resume" href="./assets/Jeremy-Resume.pdf" target="_blank"
          ><i class="fa-solid fa-download"></i> Download Resume
        </a>
      </p>
    </div>
  </section>

  <section class="section--page">
    <div id="socials--list">
      {#each socialLinks as { href, icon, text }}
        <a {href} target="_blank" rel="noopener noreferrer" class="profiles">
          <i class={icon}></i>
          {text}
        </a>
      {/each}
    </div>
  </section>

  <section class="section--page">
    <h2><i class="fa-solid fa-bolt"></i> Summary</h2>
    <p>
      <small>
        I specialize in Full Stack Software Engineering, combining expertise in front-end and back-end development, with proficiency in JavaScript, TypeScript, C#, Python, Ruby, and Solidity. I focus on building scalable enterprise software and integrating machine learning solutions, particularly Natural Language Processing (NLP) and AI-driven features. My work spans developing cloud-native applications and leveraging AI technologies to enhance software performance.
      </small>
      <br />
      <br />
      <small
        >Born and raised in Houston, I’ve built my career by contributing to companies such as Cognizant and Squarespace, and since 2021, I have worked on various full-stack projects across diverse industries. Passionate about cutting-edge technology, I strive to stay ahead of industry trends, continuously integrating cloud services like AWS and Azure with AI workflows to build innovative, impactful solutions.</small
      >
    </p>
  </section>

  <section id="work-history-wrapper" class="section--page">
    <h2><i class="fa-solid fa-briefcase"></i> Work</h2>

    <div class="card--work-history">
      Senior Software Engineer @
      <strong class="company"
        ><a href="https://www.cognizant.com/" target="_blank" rel="noopener noreferrer"
          >Cognizant</a
        ></strong
      >
      <p>
        <i>Jul 2021 till now</i> • Houston
      </p>
    </div>

    <div class="card--work-history">
      Senior Software Engineer @
      <strong class="company"
        ><a href="https://convoy.com/" target="_blank" rel="noopener noreferrer"
          >Convoy</a
        ></strong
      >
      <p><i>Nov 2019 till Jun 2021</i> • Houston</p>
    </div>

    <div class="card--work-history">
      Software Engineer @
      <strong class="company"
        ><a
          href="https://www.squarespace.com/"
          target="_blank"
          rel="noopener noreferrer">SquareSpace</a
        ></strong
      >
      <p><i>Jul 2022 till Dec 2022</i> • Houston</p>
    </div>
  </section>

  <section id="work-history-wrapper" class="section--page">
    <h2><i class="fa-solid fa-graduation-cap"></i> Education</h2>
    <div class="card--work-history">
      <strong>University of Texas at Austin</strong>
      <p>Bachelor of Science, Computer Engineering</p>
      <p>2012 - 2016</p>
    </div>
  </section>

  <section id="projects-wrapper" class="projects--page">
    <h2>
      <i class="fa-solid fa-diagram-project"></i> Projects •
      <a href="/projects">view all</a>
    </h2>
    <div class="card--work-history">
      <strong>EET</strong> •
      <a href="https://eet.et" target="_blank" rel="noopener noreferrer">demo</a>
      <p>
        <small>
          NFT project for the AI-powered fortune-telling experience on the blockchain.
        </small>
      </p>
      <p>Tech used:</p>
      <ul>
        <li>Next.js</li>
        <li>Tailwind</li>
        <li>Solidity</li>
        <li>Large Language Models (LLM)</li>
        <li>OpenAI</li>
      </ul>
    </div>

    <div class="card--work-history">
      <strong>Personal LLM</strong>
      •
      <a href="/chat">demo</a>
      <p>
        <small>
          My personal assistant who knows about me and can provide general info
          too!
        </small>
      </p>
      <p>Tech used:</p>
      <ul>
        <li>Go</li>
        <li>Large Language Models (LLM)</li>
        <li>Meta's LLaMa 3.2 3B</li>
        <li>Cloudflare Workers AI</li>
      </ul>
    </div>

  </section>

  <section class="section--page">
    <h2><i class="fa-solid fa-microchip"></i> Tech</h2>

    <div id="wrapper--techstack__items">
      {#each techStack as group}
        <div class="card--techstack">
          <small>
            {#each group as { href, text }, i}
              <a {href} target="_blank" rel="noopener noreferrer">{text}</a
              >{#if i < group.length - 1}
                {", "}
              {/if}
            {/each}
          </small>
        </div>
      {/each}
    </div>
  </section>

  <a href="./assets/Jeremy-Resume.pdf" target="_blank"
    ><hr class="center-ball" /></a
  >
  <section class="section--page section--page-text-center footer">
    <p>
      <a target="_blank" rel="noopener noreferrer" href="https://kit.svelte.dev"
        >Made with <i class="fa-solid fa-heart"></i> using SvelteKit</a
      >
      🚧
      <a
        target="_blank"
        rel="noopener noreferrer"
        href="https://github.com/devcrati/personal-website">Fork me on GitHub</a
      >
    </p>
  </section>
</div>

<svelte:head>
  <title>{title} • Portfolio</title>
</svelte:head>
