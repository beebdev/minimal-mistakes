---
layout: home
author_profile: true
---

<style>
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&family=Inconsolata:wght@600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;1,100;1,200;1,300;1,400;1,500;1,600;1,700&family=Inconsolata:wght@600&family=Noto+Serif:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Major+Mono+Display&display=swap');

.a-font {
  font-family: "IBM Plex Mono", monospace;
  font-weight: 700;
  font-style: normal;
  /* ==== */
}

.no-copy {
  -webkit-user-drag: none; /* Prevents dragging on Webkit browsers */
  user-drag: none; /* Prevents dragging on non-Webkit browsers */
  -webkit-user-select: none; /* Prevents text selection on Webkit browsers */
  -moz-user-select: none; /* Prevents text selection on Firefox */
  -ms-user-select: none; /* Prevents text selection on Internet Explorer/Edge */
  user-select: none; /* Prevents text selection on non-Webkit browsers */
  pointer-events: none; /* Prevents click events such as right-click save image */
}

.b-font {
  /* font-family: "Noto Serif", serif;
  font-optical-sizing: auto;
  font-weight: 500;
  font-style: normal;
  font-variation-settings:
    "wdth" 100; */
  text-align: justify;
}

.c-font {
  /* font-family: "Permanent Marker", cursive;
  font-weight: 400;
  font-style: normal; */

  /*=====*/
  font-family: "Major Mono Display", monospace;
  font-weight: 500;
  font-style: italic;

  /* Background color similar to a text editor */
  background-color: #f5f5f5; /* Light grey background */
  color: #333333; /* Dark grey color for text for better readability */

  /* Padding and border to mimic a text editor */
  padding: 8px;
  border-radius: 4px;

  /* Optional: box shadow to give a slight elevation like VSCode */
  box-shadow: 0px 2px 5px rgba(0,0,0,0.1);

  /* To mimic a full-width code block editor style */
  display: block; /* or 'inline-block' if you want to keep the text inline */
  width: 100%;
  box-sizing: border-box;

  /* Additional VSCode-like stylings */
  white-space: pre; /* Maintains whitespace formatting */
  overflow: auto; /* Adds horizontal scrolling if needed */
}

/* footnote */
.footnote-ref {
  font-size: smaller;
  vertical-align: super;
}

.footnote {
  font-size: smaller;
  color: #333; /* Dark grey text color */
  background-color: #f2f2f2; /* Light grey background */
  padding: 7px 10px 2px 10px; /* Top, Right, Bottom, Left */
  border-radius: 5px; /* Optional: adds rounded corners */
}

.footnote-backref {
  text-decoration: none;
  font-size: smaller;
}

.two-column {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.column {
    flex: 3;
    padding-right: 20px; /* Add space between the columns */
    margin-top: 0em; /* Adjusts space between list items, if necessary */
}

.column ul, .column ol .column li {
    margin: -10px 0px 5px 0px;
    padding-left: 20px; /* Adjusts space on the left side of the list */
}

.column2 {
  flex: 1;
}

.column:last-child {
  padding-right: 0; /* Ensure that the last column doesn't have padding on the right */
}

@media (max-width: 768px) {
  .two-column {
    flex-direction: column;
    padding-right: 0;
    flex: none;
    width: 100%;
  }
  .column {
    padding-right: 0; /* Remove padding on smaller screens */
  }
  .column2 {
    display: none;
  }

  .b-font {
    text-align: left;
  }
}

</style>

<div class="terminal">
    <div class="terminal-header">
        <p>BEEBDEV V1.0</p>
    </div>
    <div class="terminal-content">
      <pre>
██████╗ ███████╗███████╗██████╗    ██████╗  █████╗  ██████╗ ███████╗
██╔══██╗██╔════╝██╔════╝██╔══██╗   ██╔══██╗██╔══██╗██╔════╝ ██╔════╝
██████╔╝█████╗  █████╗  ██████╔╝   ██████╔╝███████║██║  ███╗█████╗  
██╔══██╗██╔══╝  ██╔══╝  ██╔══██╗   ██╔═══╝ ██╔══██║██║   ██║██╔══╝  
██████╔╝███████╗███████╗██████╔╝██╗██║     ██║  ██║╚██████╔╝███████╗
╚═════╝ ╚══════╝╚══════╝╚═════╝ ╚═╝╚═╝     ╚═╝  ╚═╝ ╚═════╝ ╚══════╝
        </pre>
        <hr>
        <h1>Hello world!</h1>
        <h2>> WHOAMI</h2>
        <p>I am a research engineer at <a href="https://www.audinate.com/">Audinate</a> working on the embedded systems and computer systems side of the industry leading audio networking standard <a href="https://www.getdante.com/meet-dante/what-is-dante/">Dante</a>.</p>
        <h2>> HISTORY</h2>
        <p>Prior to Audinate, I earned my <i>B.Eng (Hons) in Computer Engineering</i> degree from UNSW Sydney. My honours research was on designing cost-effective hw-sw co-design systems for selective genome sequencing (nanopore). I also taught undergraduate comp courses at UNSW CSE as a tutor, lecturer, coordinator and lab assistant.</p>
        <h2>> ./NEXT.SH</h2>
        <p>I'll be starting an <i>ECE PhD at Cornell University</i>'s <a href="https://www.csl.cornell.edu/">CSL</a> in Fall 2024!</p>
        <hr>
        <h2>> CAT AREAS_OF_INTEREST.TXT</h2>
        <div class="terminal-block">
          <div class="terminal-inner">
            <p>embedded systems | computer architecture | networks | bioinformatics</p>
          </div>
        </div>
    </div>
</div>

<!-- # Experience -->
---
<h1 class="a-font">Experience</h1>

<!-- ===== Audinate ===== -->

**Audinate, CTO Office**, Sydney, Australia\\
Research Engineer II<span style="float:right;">_Aug 2023 - **Present**_</span>\\
Research Engineer I<span style="float:right;">_Jan 2022 - Jul 2023_</span>\\
Research and Development Intern<span style="float:right;">_May 2021 - Aug 2021_</span>\\
Research and Development Intern<span style="float:right;">_2020 Summer_</span>\\
Research and Development Intern<span style="float:right;">_2019 Summer_</span>

<!-- ===== UNSW CSE ===== -->

**UNSW, School of CSE**, Sydney, Australia\\
Casual Academic <span style="float:right;">_Feb 2020 - **Present**_</span>

<!-- ===== UNSW Embedded Systems Research Group ===== -->

**UNSW, Embedded Systems Research Group**, Sydney, Australia\\
Undergraduate Researcher <span style="float:right;">_Nov 2020 - May 2022_</span>


<!-- # Education -->
---
<h1 class="a-font">Education</h1>

**University of New South Wales (UNSW)**, Sydney, Australia \\
B.Eng. (Honours) in Computer Engineering <span style="float:right;">_Feb 2018 - Dec 2021_</span>
<div class="two-column">
  <div class="column" markdown="1">
  - First Class Honours
  - Thesis title: _"Hardware Accelerated Real-Time Selective Genome Sequencing"_
  - Advisor: [Prof. Sri Parameswaran](https://www.sydney.edu.au/engineering/about/our-people/academic-staff/sri-parameswaran.html), (co-advised by: [Dr. Hasindu Gamaarachchi](https://www.unsw.edu.au/staff/hasindu-gamaarachchi) and [Dr. Hassaan Saadat](https://www.linkedin.com/in/hassaan-saadat-7947a3166))
  </div>
  <div class="column2">
      <img src="assets/images/logo/unsw.png" alt="UNSW logo" class="align-right no-copy" width="100" height="auto" />
  </div>
</div>

<!-- # Honours and Awards -->
---
<h1 class="a-font">Honours and Awards</h1>

**First Class Honours**, UNSW Faculty of Engineering <span style="float:right;">_2021_</span>\\
**Outstanding Undergraduate Thesis**, UNSW School of CSE <span style="float:right;">_2021_</span>\\
**Dean's Honours List**, UNSW Faculty of Engineering <span style="float:right;">_2018, 2019, 2020_</span>

<!-- # Teaching experience -->
---
<h1 class="a-font">Teaching experience</h1>

**[COMP3601](https://www.handbook.unsw.edu.au/undergraduate/courses/2021/COMP3601?year=2022) Design Project A** <span style="float:right;"> UNSW Sydney</span>\\
Guest Lecturer <span style="float:right;"> _23T3_</span>\\
Course Coordinator & Guest Lecturer, 46 students <span style="float:right;"> _22T3_</span>\\
Academic Tutor, 48 students <span style="float:right;"> _21T3_</span>

**[DESN2000](https://www.handbook.unsw.edu.au/undergraduate/courses/2023/DESN2000?year=2023) Eng. Design and Prof. Practice (COMP)** <span style="float:right;"> UNSW Sydney</span>\\
Academic Tutor & Guest Lecturer, 51 students <span style="float:right;"> _23T2_</span>

**[COMP2121](https://www.handbook.unsw.edu.au/undergraduate/courses/2020/COMP2121?year=2020) Microprocessors and Interfacing** <span style="float:right;"> UNSW Sydney</span>\\
Academic Tutor, 43 students <span style="float:right;"> _20T1_</span>

**[COMP1521](https://www.handbook.unsw.edu.au/undergraduate/courses/2021/COMP1521/?year=2021) Computer Systems Fundamentals** <span style="float:right;"> UNSW Sydney</span>\\
Academic Tutor, 46 students <span style="float:right;"> _21T2_</span>

<!-- # Advising
Katelyn Mak (with H. Gamaarachchi), *UNSW Honours Thesis* <span style="float:right;">*2023 - Present*</span> -->

<!-- # Professional Services -->
---
<h1 class="a-font">Professional Services</h1>


**External Reviewer**\\
ASP-DAC<span style="float:right;">_2024_</span>

---
<!-- # Extracurricular Activities -->
<h1 class="a-font">Extracurricular Activities</h1>

**[UNSW CSESoc](https://www.csesoc.unsw.edu.au/) Peer Mentor** <span style="float:right;">*2021*</span>\\
**[UNSW CSESoc](https://www.csesoc.unsw.edu.au/) Media Subcommittee** <span style="float:right;">*2019*</span>