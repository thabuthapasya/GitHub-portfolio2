import React from "react";
import styles from "./Portfolio.module.css";

const projects = [
  {
    title: "Project One",
    description: "A brief description of project one.",
    link: "#",
    image: "https://via.placeholder.com/300x200"
  },
  {
    title: "Project Two",
    description: "A brief description of project two.",
    link: "#",
    image: "https://via.placeholder.com/300x200"
  },
  // Add more projects as needed
];

export default function Portfolio() {
  return (
    <div className={styles.container}>
      <header className={styles.header}>
        <img
          src="https://avatars.githubusercontent.com/u/9919?s=200&v=4"
          alt="Profile"
          className={styles.profile}
        />
        <h1>Your Name</h1>
        <p className={styles.subtitle}>Web Developer | Designer | Creator</p>
        <nav className={styles.nav}>
          <a href="#about">About</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav>
      </header>

      <section id="about" className={styles.section}>
        <h2>About Me</h2>
        <p>
          I am a passionate web developer with experience in building modern web
          applications. I love creating beautiful and functional user
          experiences.
        </p>
      </section>

      <section id="projects" className={styles.section}>
        <h2>Projects</h2>
        <div className={styles.projectsGrid}>
          {projects.map((project, idx) => (
            <div className={styles.projectCard} key={idx}>
              <img src={project.image} alt={project.title} />
              <h3>{project.title}</h3>
              <p>{project.description}</p>
              <a href={project.link} target="_blank" rel="noopener noreferrer">
                View Project
              </a>
            </div>
          ))}
        </div>
      </section>

      <section id="contact" className={styles.section}>
        <h2>Contact</h2>
        <form className={styles.contactForm}>
          <input type="text" placeholder="Your Name" required />
          <input type="email" placeholder="Email Address" required />
          <textarea placeholder="Your Message" required />
          <button type="submit">Send Message</button>
        </form>
      </section>

      <footer className={styles.footer}>
        &copy; {new Date().getFullYear()} Your Name. All rights reserved.
      </footer>
    </div>
  );
}
