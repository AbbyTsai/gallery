<script>
let projects=[
    {index:1,topic:'LifeBall',about:"The video shows how-to style button in one-click!",url:'https://bordercss.netlify.app/',description:"visual corner tool: border-radius!",video:'https://www.youtube.com/embed/25PZ9mcWOtI',img:'https://img.youtube.com/vi/25PZ9mcWOtI/0.jpg'},
    {index:2,topic:'LuckyEgg',about:"The video shows how-to style background in one-click!",url:'https://luckyegg-css.netlify.app/', description:"visual background tool: gradient!",video:'https://www.youtube.com/embed/IMyj3BA_pMs',img:'https://img.youtube.com/vi/IMyj3BA_pMs/0.jpg'},
    {index:3,topic:'Hello-GUI-Challenge',about:"The video outlines all topics of challenge on how-to build interfaces!",url:'https://hello-gui-challenge.netlify.app/', description:"fantastic interface materials!",video:'https://www.youtube.com/embed/UYBhSUTjkQ8',img:'https://img.youtube.com/vi/UYBhSUTjkQ8/0.jpg'},
];
let tabs=[
{index:1,name:'who',content:"Like everyone, Abby has a pair of eyes, ears and a single nose, mouse, normaly enough, but a thing embarrased said Abby might be at top grades in near-sightedness with around 10 diopters. Woo! don't believe our eyes. It's exxxxxxtra high myopia. Cool, we may see Abby with double thick lens O_O , or contact lens on face."},
{index:2,name:'what project',content:'projects'},
{index:3,name:'why',content:"Actually, we are all grow by the past. But, do we really pay the things for the past? We may track things in newly technology most time. Just like price strategy, brand new things may be popular than outdated. YES, we may pay the poential in upgrading things. Don't we we we we we we?"},
];
let value=1;
const onclick=tabvalue=>()=>(value=tabvalue);
</script>

<div class="tabarea" id="tabarea">
{#each tabs as tab, i}
<button class="tab" on:click={onclick(tab.index)}>
{tab.name}</button>
{/each}
</div>
{#each tabs as tab, i}
{#if 2==value==tab.index}

<div class="project">
{#each projects as project, i}

<div>
<img alt="project" src={project.img} loading="lazy">
<button><a href="#dialog{i}">open</a></button>
</div>
{/each}
</div>

{#each projects as project, i}
<div class="dialog" id="dialog{i}">
<div class='dialogContent'>
<h3><a href={project.url}>{project.topic}</a></h3>
<div class="description">{project.description}</div>
<div class="about">{project.about}</div>
<iframe height="90%" width="90%" src={project.video} title="youtube">
</iframe>
<button><a href="#tabarea">back</a></button>
</div>
</div>
{/each}

{:else if value==tab.index}
<div id="tab{tab.index}" class="tabcontent">
{tab.content}
</div>
{/if}
{/each}

<style>
.about{
    text-align:center;
    padding:0 1em 0.5em 1em;
}
button{
    border:5px solid pink;
    border-radius:55% 6% 61% 84% / 83% 92% 46% 74%;
    background:pink;  
    font-weight:bold;
}
.dialogContent button, .project button{
        margin:0.5em;
}
button a{
    text-decoration:none;
}
button:hover{
    background:lightblue;
}
.project img{
    object-fit:cover;
    border:5px solid pink;
    border-radius:28% 12% 72% 88% / 90% 28% 20% 35%;
    height:80%;
    width:100%;
}
.dialog{
	height:100vh;
	width:100vw;
	background:lightblue;
    display:none;
	z-index:100;
	position:fixed;
	top:0;
}
.dialog:target, .dialog:focus{
	display:block;
}
.dialogContent{
	display:flex;
    flex-direction:column;
    height:100vh;
	width:100vw;
    align-items: center;
    justify-content: center;
}
.tab:focus{
    background:lightblue;
}
#tab2{
    display:none;
}
.tabarea{
    display:flex;
    justify-content:space-around;
    align-items:flex-end;
    height:5vh;  
}
.tab{
    width:33.33%;
    text-align:center;
    border:10px solid lightblue;
    border-radius:55% 47% 35% 20% / 46% 62% 0% 0%;
    height:2em;
    font-size:24px;
    font-weight:bold;
    text-transform: uppercase;
    background:pink;
}
.tabcontent, .project{
    background:lightblue;
    text-align:center;
    display:flex;
    align-items:center;
    justify-content:center;
    max-width:100%;
    min-width:30ch;
}
.tabcontent{
    height:55vh; 
}
.project{
    display:flex;
    justify-content:space-around;
    align-items:center;
}
iframe{
    border:15px solid pink;
    border-radius:28% 12% 72% 88% / 90% 28% 20% 35%;
    margin:0 1em;
}
.project div{
    border:10px solid pink;
    border-radius:28% 12% 72% 88% / 90% 28% 20% 35%;
    height:75%;
    width:33%;
    display:flex;
    align-items:center;
    justify-content:center;
    flex-direction:column;
    margin:0.5em;
    padding:0.5em;
}
@media screen and (min-width:1201px){
.tabcontent{
    padding:0 5em;
}
.tabcontent {
    font-size:26px;
}
.project{
    height:55vh;
    width:calc(100vw-5em);
}
.tabcontent, .project, .tabarea{
   width:calc(100vw-2em);
}
}
@media (min-width:481px) and (max-width:1200px){
.tabcontent{
    padding:0 5em;
}
.tabcontent {
    font-size:20px;
}
.project{
    height:55vh;
    width:calc(100vw-5em);
}
.tabcontent, .project, .tabarea{
   width:calc(100vw-2em);
}
}
@media screen and (max-width:480px){
.tab:nth-child(2){
   line-height:1.3em;
}
.tabcontent{
    padding:0 1em;
}
.tabcontent {
    font-size:14px; 
}
.tabcontent, .project, .tabarea{
   width:calc(100vw-3em);
}
.project{
flex-direction:column;
padding-top:1em;
}
.project div{
    width:80vw;
}
}
</style>