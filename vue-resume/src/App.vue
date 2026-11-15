<script setup lang="ts">
import DetailsCard from '@/components/DetailsCard.vue'
import SideSection from '@/components/SideSection.vue'
import MainSection from '@/components/MainSection.vue'
import SkillCard from '@/components/SkillCard.vue'
import LanguageCard from '@/components/LanguageCard.vue'
import EducationCard from '@/components/EducationCard.vue'
import JobCard from '@/components/JobCard.vue'
import ProjectCard from '@/components/ProjectCard.vue'

interface SkillGroup {
  group: string
  subSkills: string[]
}

interface Education {
  startDate: Date
  endDate: Date
  grade: string
  subject: string
  institution: string
  location: string
}

interface Job {
  startDate: Date
  endDate: Date
  position: string
  company: string
  location: string
  points: string[]
}

interface Project {
  name: string
  startDate: Date
  endDate?: Date
  position: string
  associatedWith?: string
  link?: string
  technologies?: string[]
  technologyGroups?: { label: string; items: string[] }[]
  points: string[]
}

const hardSkills: SkillGroup[] = [
  {
    group: 'Backend Development',
    subSkills: ['C# / .NET', 'Entity Framework', 'PHP / Symfony', 'Python', 'Strapi', 'REST APIs'],
  },
  {
    group: 'Frontend Development',
    subSkills: ['React', 'Vue', 'Twig', 'HTML', 'CSS', 'Responsive web design'],
  },
  {
    group: 'Databases',
    subSkills: ['PostgreSQL', 'MySQL', 'SQL', 'Database migrations'],
  },
  {
    group: 'Development Tools',
    subSkills: ['Docker', 'Git', 'GitHub', 'Debugging', 'Technical documentation'],
  },
  {
    group: 'Systems',
    subSkills: ['Linux', 'Windows'],
  },
]

const softSkills: string[] = [
  'Analytical thinking',
  'Problem-solving',
  'Communication',
  'Eager to learn',
  'Teamwork',
]

const education: Education[] = [
  {
    startDate: new Date(2024, 8),
    endDate: new Date(2026, 5),
    grade: 'Associate Degree',
    subject: 'Programming',
    institution: 'Hogeschool PXL',
    location: 'Hasselt',
  },
  {
    startDate: new Date(2016, 8),
    endDate: new Date(2020, 5),
    grade: 'Technical Secondary Diploma',
    subject: 'Electrical Installation Techniques',
    institution: 'Provil',
    location: 'Lommel',
  },
]

const jobs: Job[] = [
  {
    startDate: new Date(2025, 10),
    endDate: new Date(2026, 4),
    position: 'Junior Software Developer',
    company: 'PXL smart-ICT (internship)',
    location: 'Hasselt',
    points: [
      'Developed new features and fixed bugs in existing web applications.',
      'Worked on NaarSchoolInVlaanderen, Sint-Vincentius and DigitaalZorgkompas.',
      'Collaborated in a multidisciplinary team with developers, a designer and a scrum master.',
    ],
  },
  {
    startDate: new Date(2023, 11),
    endDate: new Date(2024, 7),
    position: 'Operator',
    company: 'Group Ceyssens',
    location: 'Heusden-Zolder',
    points: [],
  },
  {
    startDate: new Date(2021, 2),
    endDate: new Date(2023, 9),
    position: 'EMC Assistant',
    company: 'Melexis',
    location: 'Tessenderlo',
    points: [
      'Performed EMC tests using LabVIEW, TESEQ software, oscilloscopes and other laboratory equipment.',
      'Configured test setups for various test scenarios.',
      'Processed test data using Python and generated charts and reports.',
      'Soldered SMD components onto PCBs for testing purposes.',
    ],
  },
  {
    startDate: new Date(2020, 9),
    endDate: new Date(2021, 0),
    position: 'Electrician',
    company: 'Gielen Nv',
    location: 'Lommel',
    points: [],
  },
  {
    startDate: new Date(2020, 6),
    endDate: new Date(2020, 7),
    position: 'Electrician',
    company: 'Kempische Bordenbouw',
    location: 'Balen',
    points: [],
  },
]

const projects: Project[] = [
  {
    name: 'Webshop-PXL',
    link: 'https://github.com/LeviGoossensPXL/Webshop-PXL',
    startDate: new Date(2026, 1),
    associatedWith: 'School & Personal',
    position: 'Software Developer',
    technologies: ['ASP.NET', 'EntityFramework', 'PostgresSQL', 'Blazor', 'Docker'],
    points: [
      'Create issues, review code, write documentation and lead the project.',
      'Set up external login with <b>Google</b>.',
      'Set up <b>.NET</b>, <b>hosting</b> and <b>docker compose</b>.',
      'Write service classes, repository classes, API endpoints all following <b>clean architecture</b> principles.',
    ],
  },
  {
    name: 'Sint-Vincentius App',
    startDate: new Date(2026, 1),
    endDate: new Date(2026, 5),
    associatedWith: 'PXL smart-ICT',
    position: 'Software Developer | Graduation Project',
    technologyGroups: [
      { label: 'Backend', items: ['C#', 'Entity Framework', 'Docker', 'PostgreSQL'] },
      { label: 'Frontend', items: ['TypeScript', 'React'] },
    ],
    points: [
      'Migrated an existing .NET application from a single-tenant to a multi-tenant architecture.',
      'Developed a data import tool and updated the Docker configuration.',
      'Identified user needs through interviews with various Sint-Vincentius branches.',
      'Wrote technical documentation for maintenance and handover.',
    ],
  },
  {
    name: 'DigitaalZorgkompas',
    startDate: new Date(2026, 1),
    endDate: new Date(2026, 5),
    associatedWith: 'PXL smart-ICT',
    position: 'Software Developer',
    technologyGroups: [
      { label: 'Backend', items: ['TypeScript', 'Strapi', 'Docker'] },
      { label: 'Frontend', items: ['TypeScript', 'Vue'] },
    ],
    points: [
      'Developed a new TypeScript web application.',
      'Built new features and maintained documentation.',
    ],
  },
  {
    name: 'NaarSchoolInVlaanderen',
    startDate: new Date(2025, 10),
    endDate: new Date(2026, 5),
    associatedWith: 'PXL smart-ICT',
    position: 'Software Developer',
    technologies: ['PHP', 'Symfony', 'Twig', 'MySQL', 'Docker'],
    points: [
      'Extended and maintained an existing PHP application.',
      'Developed new features based on client needs.',
      'Analysed and fixed reported bugs.',
      'Wrote and updated technical documentation.',
    ],
  },
]

const printResume = () => window.print()
</script>

<template>
  <div class="action-bar">
    <button class="btn btn-primary" @click="printResume">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg>
      Print / Save as PDF
    </button>
  </div>

  <div class="cv-container">
    <!-- PAGE 1 -->
    <div class="page">
      <!-- Top Header -->
      <header class="header-banner">
        <div></div>
        <div class="header-title-box">
          <h1 class="name">LEVI GOOSSENS</h1>
          <div class="job-title">Software Developer</div>
        </div>
      </header>

      <!-- Main Columns -->
      <div class="cv-body">
        <!-- Left Sidebar -->
        <aside class="sidebar">
          <div class="photo-container">
            <img src="/profile.png" alt="Levi Goossens" class="profile-photo" />
          </div>

          <!-- Contact Details -->
          <DetailsCard
            phone-number="+32 490 25 91 20"
            email="levi.goossens107@gmail.com"
            location="Leopoldsburg, Belgium"
            linkedin-link="https://www.linkedin.com/in/levi-goossens-5462b1332/"
            github-link="https://github.com/LeviGoossensPXL"
          ></DetailsCard>

          <!-- Hard Skills -->
          <SideSection title="Hard Skills">
            <ul class="skills-list">
              <SkillCard
                v-for="skillGroup in hardSkills"
                :key="skillGroup.group"
                :group-skill="skillGroup.group"
                :sub-skills="skillGroup.subSkills"
              ></SkillCard>
            </ul>
          </SideSection>

          <!-- Soft Skills -->
          <SideSection title="Soft Skills">
            <ul class="skills-list">
              <li v-for="skill in softSkills" :key="skill">{{ skill }}</li>
            </ul>
          </SideSection>

          <!-- Languages -->
          <SideSection title="Languages">
            <LanguageCard language="Dutch" grade="Native"></LanguageCard>
            <LanguageCard language="English" grade="Very good"></LanguageCard>
          </SideSection>
        </aside>

        <!-- Right Main Column -->
        <main class="main-content">
          <!-- About Me -->
          <MainSection title="About Me">
            <p class="about-text">
              Junior software developer with experience in C#/.NET, TypeScript, PHP and Python.
              During my internship at PXL smart-ICT, I worked on web applications for real
              clients, from new features and bug fixes to documentation and data imports. I am a
              quick learner, work accurately and communicate effectively with developers,
              designers and other stakeholders. I am looking for a team where I can further
              develop my technical skills and deliver reliable software.
            </p>
          </MainSection>

          <!-- Education -->
          <MainSection title="Education">
            <template #icon>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10v6M2 10l10-5 10 5-10 5z"></path><path d="M6 12v5c3 3 9 3 12 0v-5"></path></svg>
            </template>
            <div class="timeline">
              <EducationCard
                v-for="item in education"
                :key="item.grade"
                :start-date="item.startDate"
                :end-date="item.endDate"
                :grade="item.grade"
                :subject="item.subject"
                :institution="item.institution"
                :location="item.location"
              ></EducationCard>
            </div>
          </MainSection>

          <!-- Work Experience -->
          <MainSection title="Work Experience">
            <template #icon>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="14" x="2" y="7" rx="2" ry="2"></rect><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"></path></svg>
            </template>
            <div class="timeline">
              <JobCard
                v-for="job in jobs"
                :key="`${job.company}-${job.startDate.getTime()}`"
                :start-date="job.startDate"
                :end-date="job.endDate"
                :position="job.position"
                :company="job.company"
                :location="job.location"
                :points="job.points"
              ></JobCard>
            </div>
          </MainSection>
        </main>
      </div>
    </div>

    <!-- PAGE 2: Projects -->
    <div class="page">
      <div class="cv-body single-col">
        <MainSection title="Projects">
          <template #icon>
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="12 2 2 7 12 12 22 7 12 2"></polygon><polyline points="2 17 12 22 22 17"></polyline><polyline points="2 12 12 17 22 12"></polyline></svg>
          </template>
          <div class="timeline">
            <ProjectCard
              v-for="project in projects"
              :key="project.name"
              :name="project.name"
              :start-date="project.startDate"
              :end-date="project.endDate"
              :position="project.position"
              :associated-with="project.associatedWith"
              :link="project.link"
              :technologies="project.technologies"
              :technology-groups="project.technologyGroups"
              :points="project.points"
            ></ProjectCard>
          </div>
        </MainSection>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
