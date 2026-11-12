<script setup lang="ts">
import ProjectCard from '@/components/ProjectCard.vue'
import JobCard from '@/components/JobCard.vue'
import EducationCard from "@/components/EducationCard.vue";
import SkillCard from '@/components/SkillCard.vue'
import SideSection from '@/components/SideSection.vue'
import DetailsCard from '@/components/DetailsCard.vue'

const date1: Date = new Date(2026, 1)
const date2: Date = new Date(2026, 5)

const date3: Date = new Date(2021, 2)
const date4: Date = new Date(2023, 9)

const date5: Date = new Date(2024, 8)
const date6: Date = new Date(2026, 5)
</script>

<template>
  <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
  <EducationCard
      :start-date="date5"
      :end-date="date6"
      grade="Graduaat"
      subject="Programmeren"
      institution="Hogeschool PXL"
      location="Hasselt"></EducationCard>

  <ProjectCard
    name="Sint-Vincentius-app"
    :startDate="date1"
    :endDate="date2"
    position="Developer"
    associatedWith="PXL smart-ICT"
    :points="['a', 'b', 'c']"
    :technologies="['C#', 'javascript']"
  ></ProjectCard>
  <SideSection title="Werkervaring">
  <JobCard
    location="Tessenderlo"
    :startDate="date3"
    :endDate="date4"
    position="EMC-Assistant"
    company="Melexis"
    :points="['a', 'b', 'c']"
    :technologies="['C#', 'javascript']"
  ></JobCard>
  </SideSection>
  <SkillCard
      groupSkill="Backend Development"
      :subSkills="['C# / Entity Framework', 'PHP / Symfony', 'Python', 'Strapi', 'REST APIs']"
  ></SkillCard>
  <DetailsCard
      phoneNumber="+32490259120"
      email="levi.goossens107@gmail.com"
      location="Leopoldsburg, Belgie"
      linkedinLink="https://www.linkedin.com/in/levi-goossens-5462b1332"
      githubLink="https://github.com/LeviGoossens"
  ></DetailsCard>
</template>

<style scoped></style>
