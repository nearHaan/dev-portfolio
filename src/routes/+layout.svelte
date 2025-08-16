<script lang="ts">
	import '../app.css';
	let { children } = $props();

	let activeTab: string = $state('home');

	function onTabClick(newTab: string) {
		activeTab = newTab;
	}
</script>

<svelte:head>
	<title>Farhaan Nizam</title>
</svelte:head>

<div class="flex flex-col min-h-screen min-w-screen bg-black p-4 text-white">
	<header class="sticky absolute top-4 flex w-full items-center justify-center">
		<nav class="rounded-full bg-[#ffffff15] p-1 backdrop-blur-lg">
			<ul class="flex">
				<li>
					<div
						class="rounded-full px-3 py-1 {activeTab == 'home'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						<a
							onclick={() => {
								onTabClick('home');
							}}
							href="/">Home</a
						>
					</div>
				</li>
				<li>
					<div
						class="rounded-full px-3 py-1 {activeTab == 'about'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						<a
							onclick={() => {
								onTabClick('about');
							}}
							href="/">About</a
						>
					</div>
				</li>
				<li>
					<div
						class="rounded-full px-3 py-1 {activeTab == 'projects'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						<a
							onclick={() => {
								onTabClick('projects');
							}}
							href="/">Projects</a
						>
					</div>
				</li>
				<li>
					<div
						class="rounded-full px-3 py-1 {activeTab == 'experience'
							? 'bg-[#ffffff15] backdrop-blur-lg'
							: ''}"
					>
						<a
							onclick={() => {
								onTabClick('experience');
							}}
							href="/">Experience</a
						>
					</div>
				</li>
			</ul>
		</nav>
	</header>
	<main class="absolute inset-0">
		{@render children?.()}
	</main>
</div>
