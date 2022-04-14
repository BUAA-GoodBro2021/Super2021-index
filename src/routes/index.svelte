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
			web: 'https://wudao.netlify.app/'
		},
		{
			projectName: 'StarMap',
			introduction: 'TAT',
			author: '几个人&周恩申大哥',
			github: 'https://github.com/BUAA-OpenMap-Group',
			web: 'https://www.zhoues.com'
		}
	];
	function showTime() {
		var date = new Date(); //日期对象
		day = date.getFullYear() + '年'; //读英文就行了
		day = day + (date.getMonth() + 1) + '月'; //取月的时候取的是当前月-1如果想取当前月+1就可以了
		day = day + date.getDate() + '日';
		now = date.getHours() + ':';
		now = now + date.getMinutes() + ':';
		now = now + date.getSeconds();
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
			<h1 class="mb-5 text-5xl font-bold">Super2021</h1>
			<p class="mb-5">超乎你的想象</p>
			<h2 class="mb-5 text-5xl font-bold">{now}</h2>
		</div>
	</div>
</div>
{#each data as d}
	<br />
	<div class="grid grid-cols-12 gap-4">
		<div class="col-span-2" />
		<div class="card lg:card-side bg-base-100 shadow-xl  col-span-8 ">
			<!-- <figure class="max-w-6xl"><img src="src\image\super2021.png"  alt="echo"></figure> -->
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
	</div>
	<br />
{/each}
