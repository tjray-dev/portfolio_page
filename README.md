<!DOCTYPE html>
<html lang="en-US">
  <head>
    <link rel="stylesheet" href="index.css">
    <title>tateray.com</title>
  </head>
  <body class="page" style="background-color:rgba(29, 157, 216, 0.726)">
    <header class="heading">
    </header>
    <div class="content">
      <div class="blurb" id="about">
        {{about}}
      </div>
      <div class="blurb" id="stack">
        <h5>What I've been working with lately...</h5>
        <ul class="listing" id="stack">
          <li class="listItem" id="tech" v-for="tech in techStack">{{tech}}</li>
        </ul>
      </div>
      <div class="blurb" id="socials">
          <h6>The Socials</h6>
          <div class="navbar">
            <a class="navlink" v-for="social in socials" href="social.link">{{social}}</a>
          </div>
      </div>
    </div>
    <div class="projects">
      <div v-for="project in projects" class="project" :key="project.index">
        <h4><u>{{project.projectName}}</u></h4>
        <div class="thumbnail">
        </div>
        <p>
          {{project.projectDescription}}
        </p>
        <div class="navbar">
          <a class="navlink" :href="project.projectRepo">GitHub</a>
          <a class="navlink" href="project.projectDemo">Demo</a>
          <a class="navlink" href="project.projectSite">Site</a>
        </div>
      </div>
    </div>
    <script src="https://unpkg.com/vue@3"></script>
    <script>
      Vue.createApp({
        data(){
          return{
            about: "Hi, My name is Tate. Welcome to my site. I'm a Full Stack Software Engineer just beginning my journey as a developer.",
            techStack: [ "HTML",
                         "CSS",
                         "Ruby",
                         "JavaScript",
                         "Vue",
                        ],
            socials: [ "Twitter",
                       "Reddit",
                       "LinkedIn",
                      ],
            projects: [
              {
                projectName: "City of Brass",
                projectThumbnail: "an image src",
                projectDescription: "A Fantasy game; fight monsters and collect treasure.",
                projectRepo: "https://github.com/tjray-dev/city-of-brass",
                projectDemo: "a loom link",
                projectSite: "a link to the deployed site"
              },
              {
                projectName: "Growise",
                projectThumbnail: "an image src",
                projectDescription: "A Grow Journal for hydroponic growers of all skills and stripes",
                projectRepo: "https://github.com/RogueStateTechnologies/hydro",
                projectDemo: "a loom link",
                projectSite: "a link to the deployed site"
              },
            ]
          }
        }
      })
      .mount('.page')
    </script>
  </body>
</html>
