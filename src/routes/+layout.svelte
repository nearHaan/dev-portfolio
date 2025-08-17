<script lang="ts">
	import '../app.css';
	let { children } = $props();

	let activeTab: string = $state('home');

	function onTabClick(newTab: string) {
		console.log(newTab);
		activeTab = newTab;
	}
</script>

<svelte:head>
	<title>Farhaan Nizam</title>
</svelte:head>

<div class="flex min-h-screen min-w-screen flex-col bg-black p-4 text-white">
	<header class="absolute z-10 sticky top-4 flex w-full items-center justify-center font-title">
		<nav class="rounded-full bg-[#ffffff15] border-1 border-[#ffffff30] inset-shadow-xs inset-shadow-white p-[2px] backdrop-blur-lg">
			<ul class="flex">
				<li>
					<button
						onclick={() => {
							onTabClick('home');
						}}
						class="rounded-full px-4 py-0.5 {activeTab == 'home'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						Home
					</button>
				</li>
				<li>
					<button
						onclick={() => {
							onTabClick('about');
						}}
						class="rounded-full px-4 py-0.5 {activeTab == 'about'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						About
					</button>
				</li>
				<li>
					<button
						onclick={() => {
							onTabClick('projects');
						}}
						class="rounded-full px-4 py-0.5 {activeTab == 'projects'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						Projects
					</button>
				</li>
				<li>
					<button
						onclick={() => {
							onTabClick('experience');
						}}
						class="rounded-full px-4 py-0.5 {activeTab == 'experience'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						Experience
					</button>
				</li>
			</ul>
		</nav>
	</header>
	<main class="z-0 absolute inset-0">
		{@render children?.()}
	</main>
</div>
