<script>
</script>
<div id="copyright">
<div>COPYRIGHT 2022</div>
</div>
<div class="socialarea">
    <a href="https://github.com/AbbyTsai/">GitHub</a>
    <a href="https://codepen.io/AbbyTsai/">CodePen</a>
    <a href="https://twitter.com/AbbyPTsai">Twitter</a>
    <a href="https://www.linkedin.com/in/AbbyTsai">LinkedIn</a>
</div>

<style>
.socialarea{
    display:flex;
    justify-content:space-around;
    background:pink;
    height:5vh;
    align-items:center;
    position:absolute;
    width:100vw;

}
.socialarea a{
    text-decoration:none;
    font-weight:bold;
}
.socialarea a:hover{
    background:lightblue;
    border-radius:13% 86% 24% 36% / 42% 0% 48% 47%;
}
#copyright{
    font-weight:bold;
    height:5vh;
	display:flex;
    justify-content:center;
    align-items:center;
	font-size:smaller;
	background:repeating-linear-gradient(44deg, transparent 10px, lightblue 10px, lightblue 20px, transparent 20px, transparent 30px, orange 30px, orange 40px, transparent 40px, transparent 50px), repeating-linear-gradient(-44deg, white 10px, lightblue 10px, lightblue 20px, white 20px, white 30px, orange 30px, orange 40px, white 40px, white 50px);

}
@media screen and (min-width:480px){
.socialarea{
    bottom:0;
}
}
</style>