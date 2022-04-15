<script>
	import { onMount } from 'svelte';
  import { afterUpdate } from 'svelte';
  import '../app.css';
  let now = '';
  let day = '';
	let data = [
		{
			projectName: 'Wudao',
			introduction: 'QAQ',
			author: 'TualatinX,LLLeo,BITTIO,echo子懿,woarthur',
			github: 'https://github.com/WuDaoGroup',
			web: 'https://wudao.netlify.app/',
			background:"https://923259.smushcdn.com/2321054/wp-content/uploads/2019/05/what-is-data-science-1.jpg",
			bgcolor:"bg-accent"
		},
		{
			projectName: 'StarMap',
			introduction: 'TAT',
			author: '几个人&周恩申大哥',
			github: 'https://github.com/BUAA-OpenMap-Group',
			web: 'https://www.zhoues.com',
			background:"https://923259.smushcdn.com/2321054/wp-content/uploads/2019/05/what-is-data-science-1.jpg",
			bgcolor:"bg-orange-500"
		}
	];
	function completion(a){
		if(a<10){
			return '0' + a;
		}
		else{
			return a;
		}
	}
	function showTime() {
		var date = new Date(); 
		day = date.getFullYear() + '年'; 
		day = day + (date.getMonth() + 1) + '月'; 
		day = day + date.getDate() + '日';

		now = completion(date.getHours()) + ':';
		now = now + completion(date.getMinutes()) + ':';
		now = now + completion(date.getSeconds());
	}
  onMount(() => {
		console.log('the component has mounted');
    const interval = setInterval(showTime, 1000);
	});
</script>

<div class="navbar bg-neutral text-neutral-content max h-5">
	<div><img src="src\image\super2021.png" alt="super2021" width="154px" /></div>
	<a href="https://scs.buaa.edu.cn/" class="btn">云平台</a>
	<a href="https://spoc.buaa.edu.cn/" class="btn">SPOC</a>
	<a href="https://os.buaa.edu.cn/" class="btn">OS</a>
	<a href="http://lab.os.buaa.edu.cn/" class="btn">Lab</a>
	<a href="https://github.com/" class="btn">Github</a>
</div>

<div class="hero min-h-screen" style='background-image: url("src/image/super2021.png");'>
	<div class="hero-overlay bg-opacity-60" />
	<div class="hero-content text-center text-neutral-content">
		<div class="max-w-md">
			<h1 class="mb-5 text-7xl font-bold">Super2021</h1>
			<p class="mb-5 text-5xl font-bold">超乎你的想象</p>
			<h2 class="mb-5 text-6xl font-bold">{now}</h2>
		</div>
	</div>
</div>
{#each data as d}
<div class={d.bgcolor}>
	<br />
	<!-- <div class="grid grid-cols-12 gap-4">
		<div class="col-span-2" />
		<div class="card lg:card-side bg-base-100 shadow-xl  col-span-8 ">
			 <figure class="max-w-6xl"><img src="src\image\super2021.png"  alt="echo"></figure> 
			<div class="card-body">
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
	</div> -->
	<div class="grid grid-cols-12 gap-4">
		<div class="col-span-2" />
	<div class="card  bg-base-100 shadow-xl image-full col-span-8">
		<figure><img src={d.background} alt="Shoes" /></figure>
		<div class="card-body">
			<h2 class="card-title mb-5 text-7xl font-bold text-center">{d.projectName}</h2>
			<p  class="card-title mb-5 text-3xl  text-center">Intro:{d.introduction}</p>
			<p class="card-title mb-5 text-3xl  text-center">author:</p>
			<p class="card-title mb-5 text-3xl  text-center">{d.author}</p>
			<div class="card-actions justify-center">
				<a href={d.github} class="btn btn-primary">GITHUB</a>
				<a href={d.web} class="btn btn-primary">WEB</a>
			</div>
		</div>
	  </div>
	</div>
	<br />
</div>
{/each}
