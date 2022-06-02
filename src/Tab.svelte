<script>
let projects=[
    {index:1,topic:'LifeBall',url:'https://bordercss.netlify.app/',description:"visual corner tool: border-radius!"},
    {index:2,topic:'LuckyEgg',url:'https://luckyegg-css.netlify.app/', description:"visual background tool: gradient!"},
    {index:3,topic:'Hello-GUI-Challenge',url:'https://hello-gui-challenge.netlify.app/', description:"fantastic learning materials: front-end development!"},
];
let tabs=[
{index:1,name:'who',content:"Like everyone, Abby has a pair of eyes, ears and a single nose, mouse, normaly enough, but a thing embarrased said Abby might be at top grades in near-sightedness with around 10 diopters. Woo! don't believe our eyes. It's exxxxxxtra high myopia. Cool, we may see Abby with double thick lens O_O , or contact lens on face."},
{index:2,name:'what',content:'projects'},
{index:3,name:'why',content:"Actually, we are all grow by the past. But, do we really pay the things for the past? We may track things in newly technology most time. Just like price strategy, brand new things may be popular than outdated. YES, we may pay the poential in upgrading things. Don't we we we we we we?"},
];
let value=1;
const onclick=tabvalue=>()=>(value=tabvalue);
</script>

<div class="tabarea">
{#each tabs as tab, i}
<button class="tab" on:click={onclick(tab.index)}>
{tab.name}</button>
{/each}
</div>
{#each tabs as tab, i}
{#if 2==value==tab.index}
<div class="project">
{#each projects as project, i}
<div><h3><a href={project.url}>{project.topic}</a></h3>
<p>{project.description}</p></div>
{/each}
</div>
{:else if value==tab.index}
<div id="tab{tab.index}" class="tabcontent">
{tab.content}
</div>
{/if}
{/each}

<style>
.project p{
    font-size:8px;
}
.tab:nth-child(2)::before{
    content:'projects';
    position:absolute;
    top:17em;
    font-size:12px; 
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
    background:pink;
    align-items:center;
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
}
.tabcontent, .project{
    background:lightblue;
    border:5px solid pink;
    text-align:center;
    display:flex;
    align-items:center;
    justify-content:center;
}
.project{
    display:flex;
    justify-content:space-around;
    align-items:center;
}
.project div{
    border:5px solid pink;
    border-radius:28% 12% 72% 88% / 90% 28% 20% 35%;
    height:fit-content;
    width:fit-content;
    display:flex;
    align-items:center;
    justify-content:center;
    flex-direction:column;
    margin:0.5em;
    padding:0.5em;
}
.tabcontent, .project{
   padding:1em;
}
@media screen and (min-width:1201px){
 .tabcontent, .project, .tabarea{
   width:calc(100vw-15px);
}   
.tabcontent, .project{
    height:50vh;
}
}
@media (min-width:481px) and (max-width:1200px){
.tabcontent, .project, .tabarea{
   width:calc(100vw-15px);
}
.tabcontent, .project{
    height:35vh;
}
}
@media screen and (max-width:480px){
.tabcontent, .project {
   width:calc(100vw-15px);
}
.tabarea{
    width:100vw;
}
.tabcontent, .project{
   height:60vh;
}
.project{
flex-direction:column;
}
.project div{
    width:80vw;
}
}
</style>
