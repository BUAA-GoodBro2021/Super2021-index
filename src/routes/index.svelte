<script>
    import "../app.css"

    let data=[
      {
        projectName:"Wudao",
        introduction:"QAQ",
        author:"TualatinX,LLLeo,BITTIO,echo子懿,woarthur",
        github:"https://github.com/WuDaoGroup",
        web:"https://wudao.netlify.app/",
        
      },
      {
        projectName:"StarMap",
        introduction:"TAT",
        author:"几个人&周恩申大哥",
        github:"https://github.com/BUAA-OpenMap-Group",
        web:"https://www.zhoues.com",
      },

    ]
</script>






<div class="navbar bg-neutral text-neutral-content max h-5">
    <div><img src="src\image\super2021.png" alt="super2021" width="154px"></div>
    <a href="https://scs.buaa.edu.cn/" class="btn">云平台</a>
    <a href="https://spoc.buaa.edu.cn/" class="btn">SPOC</a>
    <a href="https://os.buaa.edu.cn/" class="btn">OS</a>
    <a href="http://lab.os.buaa.edu.cn/" class="btn">Lab</a>
    <a href="https://github.com/" class="btn">Github</a>
  </div>
  {#each data as d}
  <br>
<div class="grid grid-cols-12 gap-4">

  <div class="col-span-2"></div>
  <div class="card lg:card-side bg-base-100 shadow-xl  col-span-8 ">
    <!-- <figure class="max-w-6xl"><img src="src\image\super2021.png"  alt="echo"></figure> -->
    <div class="card-body" >
      <h2 class="card-title">{d.projectName}</h2>
      <p>Intro:{d.introduction}</p>
      <p>author:</p>
      <p>{d.author}</p>
      <div class="card-actions justify-end">
        <a href={d.github} class="btn btn-primary">GITHUB</a>
        <a href={d.web} class="btn btn-primary">WEB</a>
      </div>
    </div>
  </div>
 
</div>
<br>
{/each}