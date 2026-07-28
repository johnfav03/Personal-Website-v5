<script setup>
const projects = [
  {
    title: "Optimizing Compiler",
    subtitle: "EECS 483 — Compiler Construction",
    description:
      "Built an end-to-end compiler for a custom programming language, implementing lexical analysis, parsing, semantic analysis, intermediate representation, optimization passes, and code generation.",
    date: "FA 24",
    category: "Compiler",
    techs: ["Rust", "IR", "Optimization", "Compiler Design"],
    image: "compiler.png"
  },
  {
    title: "Out-of-Order Processor",
    subtitle: "EECS 470 — Computer Architecture",
    description:
      "Designed and implemented a superscalar processor microarchitecture in SystemVerilog, incorporating pipelining, instruction scheduling, branch prediction, and memory hierarchy components.",
    date: "FA 24",
    category: "Hardware",
    techs: ["SystemVerilog", "RTL", "CPU Architecture"],
    image: "processor-img.png"
  },
  {
    title: "Networked File System",
    subtitle: "EECS 482 — Operating Systems",
    description:
      "Developed a networked file system from the ground up, implementing client-server communication, file operations, and synchronization primitives while exploring distributed storage and concurrency challenges.",
    date: "FA 24",
    category: "Systems",
    techs: ["C++", "Concurrency", "Memory Management"],
    image: "filesys-img.png"
  },
    {
    title: "MBTA Predictor",
    subtitle: "Machine Learning Pipeline",
    description:
      "Built a machine learning model to predict Boston transit travel times using TensorFlow, with automated daily training and refinement through GitHub Actions.",
    date: "SM 23",
    category: "Machine Learning",
    techs: ["TensorFlow", "Python", "GitHub Actions", "MBTA API"],
    image: "mbta-pred.jpeg"
  },
{
    title: "Bombard",
    subtitle: "2nd Place — QuantUM Hackathon 2024",
    description:
      "Implemented a 3-bit quantum random number generator in Qiskit with error correction using Shor's code and connected it to IBM Cloud quantum computers as the foundation for a quantum battleship-inspired game.",
    date: "24",
    category: "Quantum",
    techs: ["Qiskit", "Python", "IBM Quantum"],
    image: "hackathon.jpeg"
  },
  {
    title: "Firefighting Car",
    subtitle: "EECS 373 - Embedded Systems",
    description:
      "Designed an embedded vehicle using dual STM32 microcontrollers with sensor integration, wireless communication, and motor control to locate simulated fires and victims.",
    category: "Embedded",
    techs: ["C", "STM32", "I2C", "SPI", "UART"],
    image: "fire-car.jpeg"
  },
    {
    title: "QSOR Scent Classifier",
    subtitle: "Graph Neural Network Research",
    description:
      "Implemented a graph convolutional neural network in PyTorch to predict molecular odors based on research literature, exploring graph representations and scientific machine learning.",
    date: "SM 24",
    category: "Machine Learning",
    techs: ["PyTorch", "Python", "GCN"],
    image: "qsor-model.jpeg"
  },
  {
    title: "Steane Decoder",
    subtitle: "EECS 479 — Quantum Computing",
    description:
      "Developed a fault-tolerant quantum error correction circuit using the Steane code, implementing encoding, decoding, and recovery operations with Qiskit.",
    date: "FA 23",
    category: "Quantum",
    techs: ["Qiskit", "Python", "Quantum Error Correction"],
    image: "steane-code.jpeg"
  },
]
</script>

<template>
    <main class="projects">

        <header class="projects-header">
            <h1>PROJECTS</h1>
        </header>

        <section class="project-grid">

            <article
                class="project-card"
                v-for="project in projects"
                :key="project.title"
            >
                                    <h2>
                            {{ project.title }}
                        </h2>

                        <h3>
                            {{ project.subtitle }}
                        </h3>

                <div class="project-main">

                    <div class="project-thumbnail">
                        <img 
                            :src="project.image"
                            :alt="project.title"
                        >
                    </div>

                    <div class="project-info">
                        <p>
                            {{ project.description }}
                        </p>

                    </div>

                </div>


                <div class="techs">

                    <span
                        v-for="tech in project.techs"
                        :key="tech"
                    >
                        {{ tech }}
                    </span>

                </div>

            </article>

        </section>

    </main>
</template>

<style scoped>
.projects {

    width:100%;
    height:100%;

    padding: clamp(3rem, 15vh, 8rem) clamp(3rem, 15vw, 14rem);

    overflow-y: auto;

    /* Firefox */
    scrollbar-width: none;

    /* IE / Edge Legacy */
    -ms-overflow-style: none;

}

/* Chrome, Safari, Edge */
.projects::-webkit-scrollbar {
    display: none;
}



.projects-header h1 {

    font-size: clamp(2rem, 3vw, 3rem);

    margin:0 0 clamp(2rem, 5vh, 4rem);

    color:var(--acc-two);

}



.project-grid {

    display:grid;

    grid-template-columns:repeat(2, minmax(0, 1fr));

    gap:clamp(1.5rem, 3vw, 3rem);

}



.project-card {

    background:rgba(255,255,255,0.03);

    border-radius:0.75rem;

    padding:1.5rem;

    /* border:3px solid rgba(255,255,255,0.05); */

    transition:
        transform 0.2s ease,
        border-color 0.2s ease;

}



.project-main {

    display:grid;

    grid-template-columns:
        clamp(5rem, 8vw, 8rem)
        1fr;

    gap:1.25rem;

}



.project-thumbnail {

    aspect-ratio:1;

    overflow:hidden;

    border-radius:0.5rem;

    border:3px solid var(--bg-dark);

}



.project-thumbnail img {

    width:100%;
    height:100%;

    object-fit:cover;

}



.project-card h2 {

    margin:0;

    font-size:clamp(1rem, 1.2vw, 1.25rem);

    font-weight:400;

    line-height:1.5;

}



.project-card h3 {

    margin:0.15rem 0 0.75rem;

    font-size:0.8rem;
    color: #777;

    font-weight:300;

}



.project-info p {

    margin:0;

    font-size:0.85rem;

    line-height:1.5;

    color:#BBB;

}



.techs {

    margin-top:1.25rem;

    padding-top:0.75rem;

    border-top:1px solid var(--acc-two);

    display:flex;

    flex-wrap:wrap;

    gap:0.5rem;

}



.techs span {

    font-size:0.75rem;

    color:#777;

}



.techs span:not(:last-child)::after {

    content:"·";

    margin-left:0.5rem;

    color:var(--acc-two);

}
</style>