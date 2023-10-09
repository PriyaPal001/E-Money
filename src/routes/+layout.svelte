<script>
	import Navbar from '$lib/home/Navbar.svelte';
	import { Home, Layout, PlusSquare } from 'lucide-svelte';
	import '../app.postcss';
	import { User } from 'lucide-svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import Label from '$lib/components/ui/label/label.svelte';
	import { enhance } from '$app/forms';
	export let data;

	let nav = {
		title: 'Svelte Tailwinds',
		img: 'https://cdn-icons-png.flaticon.com/128/10238/10238346.png',
		listnavs: [
			{
				name: 'Home',
				link: '/homee',
				icon: Home,
				color: '#bee9e8'
			},
			{
				name: 'Dashbaord',
				link: '/dashboard',
				icon: Layout
			},
			{
				name: 'Post',
				link: '/post',
				icon: PlusSquare
			},
			{
				name: 'Profile',
				link: '/profile',
				icon: User
			}
		]
	};

	let isMenu =false;
</script>

<!-- <Navbar email={data.email} />
<slot /> -->

<div>
	<!-- Off-canvas menu for mobile, show/hide based on off-canvas menu state. -->
	<div class="relative z-50 lg:hidden {isMenu ? "opacity-100 ": "opacity-0" }  transition-opacity ease-linear duration-300"  role="dialog" aria-modal="true">
		<!--
		Off-canvas menu backdrop, show/hide based on off-canvas menu state.
  
		Entering: "transition-opacity ease-linear duration-300"
		  From: "opacity-0"
		  To: "opacity-100"
		Leaving: "transition-opacity ease-linear duration-300"
		  From: "opacity-100"
		  To: "opacity-0"
	  -->
		<div class="fixed inset-0 bg-gray-900/80 {isMenu ? "translate-x-0 ": "-translate-x-full" }  transition ease-in-out duration-300 transform" />

		<div class="fixed inset-0 flex {isMenu ? "translate-x-0 ": "-translate-x-full" }  transition ease-in-out duration-300 transform">
			<!--
		  Off-canvas menu, show/hide based on off-canvas menu state.
  
		  Entering: "transition ease-in-out duration-300 transform"
			From: "-translate-x-full"
			To: "translate-x-0"
		  Leaving: "transition ease-in-out duration-300 transform"
			From: "translate-x-0"
			To: "-translate-x-full"
		-->
			<div class="relative mr-16 flex w-full max-w-xs flex-1 {isMenu ? "opacity-100 ": "opacity-0" }  transition-opacity ease-in-out duration-300">
				<!--
			Close button, show/hide based on off-canvas menu state.
  
			Entering: "ease-in-out duration-300"
			  From: "opacity-0"
			  To: "opacity-100"
			Leaving: "ease-in-out duration-300"
			  From: "opacity-100"
			  To: "opacity-0"
		  -->
				<div class="absolute left-full top-0 flex w-16 justify-center pt-5">
					<button type="button" class="-m-2.5 p-2.5" on:click={()=>{isMenu=false}}>
						<span class="sr-only">Close sidebar</span>
						<svg
							class="h-6 w-6 text-white"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
						</svg>
					</button>
				</div>

				<!-- Sidebar component, swap this element with another sidebar if you like -->
				<div class="flex grow flex-col gap-y-5 overflow-y-auto bg-white px-6 pb-2">
					<div class="flex h-16 shrink-0 items-center">
						<img class="h-10 w-auto" src={nav.img} alt="Your Company" />
					</div>
					<nav class="flex flex-1 flex-col">
						<ul role="list" class="flex flex-1 flex-col gap-y-7">
							<li>
								<ul role="list" class="-mx-2 space-y-1 ">
									{#each nav.listnavs as item}
										<li>
											<!-- Current: "bg-gray-50 text-indigo-600", Default: "text-gray-700 hover:text-indigo-600 hover:bg-gray-50" -->
											<a
												href={item.link}
												class="bg-gray-50 text-indigo-600 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold hover:translate-x-1 transition-all duration-150"
												on:click={()=>{isMenu=false}}
											>
												<svelte:component this={item.icon} size="20" strokeWidth="1.3" />
												{item.name}
											</a>
										</li>
									{/each}
								</ul>
							</li>
							<li>
								<div class="text-xs font-semibold leading-6 text-gray-400">Your teams</div>
								<ul role="list" class="-mx-2 mt-2 space-y-1">
									<li>
										<!-- Current: "bg-gray-50 text-indigo-600", Default: "text-gray-700 hover:text-indigo-600 hover:bg-gray-50" -->
										<a
											href="#"
											class="text-gray-700 hover:text-indigo-600 hover:bg-gray-50 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold"
										>
											<span
												class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
												>H</span
											>
											<span class="truncate">Heroicons</span>
										</a>
									</li>
									<li>
										<a
											href="#"
											class="text-gray-700 hover:text-indigo-600 hover:bg-gray-50 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold"
										>
											<span
												class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
												>T</span
											>
											<span class="truncate">Tailwind Labs</span>
										</a>
									</li>
									<li>
										<a
											href="#"
											class="text-gray-700 hover:text-indigo-600 hover:bg-gray-50 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold"
										>
											<span
												class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
												>W</span
											>
											<span class="truncate">Workcation</span>
										</a>
									</li>
								</ul>
							</li>
						</ul>
					</nav>
				</div>
			</div>
		</div>
	</div>

	<!-- Static sidebar for desktop -->
	<div class="hidden lg:fixed lg:inset-y-0 lg:z-50 lg:flex lg:w-60 lg:flex-col">
		<!-- Sidebar component, swap this element with another sidebar if you like -->
		<div
			class="flex grow flex-col gap-y-5 overflow-y-auto shadow-xl shadow-gray-900 bg-[#131212] px-6"
		>
			<div class="flex h-16 shrink-0 items-center">
				<img class="h-10 w-auto" src={nav.img} alt="Your Company" />
			</div>
			<nav class="flex flex-1 flex-col">
				<ul role="list" class="flex flex-1 flex-col gap-y-7">
					<li>
						<ul role="list" class="-mx-2 space-y-1">
							<li>
								<!-- Current: "bg-gray-50 text-indigo-600", Default: "text-gray-700 hover:text-indigo-600 hover:bg-gray-50" -->
								{#each nav.listnavs as items}
									<a
										href={items.link}
										class=" text-[#bee9e8] group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold hover:text-white hover:bg-gray-800 hover:translate-x-1 transition-all duration-150"
									>
										<svelte:component
											this={items.icon}
											size="20"
											strokeWidth="1.3"
											color="#bee9e8"
										/>
										{items.name}
									</a>
								{/each}
							</li>
						</ul>
					</li>

					<li class="-mx-6 mt-auto ">
						<div
							
							class="flex items-center gap-x-4 px-6 py-3 text-sm font-semibold leading-6 text-gray-900 "
						>
							<!-- <img
								class="h-8 w-8 rounded-full bg-gray-50"
								src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
								alt=""
							/> -->
							<span class="sr-only">Your profile</span>

							<div>
								{#if data.email}
									<form method="POST" action="./?/logout" use:enhance>
										<Button  size=lg type="submit" >
											<User size="18" class="mr-1" strokeWidth="2" />
											Log Out</Button
										>
									</form>
								{:else}
									<Button href="/login">
										<User size="18" class="mr-1" strokeWidth="2" />
										Log In</Button
									>
								{/if}
							</div>
						</div>
					</li>
				</ul>
			</nav>
		</div>
	</div>

	<div
		class="sticky top-0 z-40 flex items-center gap-x-6 bg-[#212529] px-4 py-4 shadow-sm sm:px-6 lg:hidden"
	>
		<button type="button" class="-m-2.5 p-2.5 text-gray-700 lg:hidden " on:click={()=>{isMenu=true}}>
			<span class="sr-only">Open sidebar</span>
			<svg
				class="h-6 w-6"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				aria-hidden="true"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
				/>
			</svg>
		</button>
		<div class="flex-1 text-sm font-semibold leading-6 text-gray-900">Dashboard</div>
		<a href="#">
			<span class="sr-only">Your profile</span>
			<img
				class="h-8 w-8 rounded-full bg-gray-50"
				src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
				alt=""
			/>
		</a>
	</div>

	<main class="lg:pl-72 bg-[#202020] h-full">
		<div class="xl:pr-96">
			<div class="px-4 py-10 sm:px-6 lg:px-8 lg:py-6">
				<!-- Main area -->
				<slot><!-- optional fallback --></slot>
			</div>
		</div>
	</main>

	<aside
		class="fixed inset-y-0 right-0 hidden bg-[#131212] shadow-xl shadow-gray-900 w-96 overflow-y-auto px-4 py-6 sm:px-6 lg:px-8 xl:block"
	>
		<li>
			<div class="text-xs font-semibold leading-6 text-gray-400">Your teams</div>
			<ul role="list" class="-mx-2 mt-2 space-y-1">
				<li>
					<!-- Current: "bg-gray-50 text-indigo-600", Default: "text-gray-700 hover:text-indigo-600 hover:bg-gray-50" -->
					<a
						href="#"
						class="text-gray-700 hover:text-white hover:bg-gray-800 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold hover:translate-x-1 transition-all duration-150"
					>
						<span
							class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
							>H</span
						>
						<span class="truncate">Heroicons</span>
					</a>
				</li>
				<li>
					<a
						href="#"
						class="text-gray-700 hover:text-white hover:bg-gray-800 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold hover:translate-x-1 transition-all duration-150"
					>
						<span
							class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
							>T</span
						>
						<span class="truncate">Tailwind Labs</span>
					</a>
				</li>
				<li>
					<a
						href="#"
						class="text-gray-700 hover:text-white hover:bg-gray-800 group flex gap-x-3 rounded-md p-2 text-sm leading-6 font-semibold hover:translate-x-1 transition-all duration-150"
					>
						<span
							class="flex h-6 w-6 shrink-0 items-center justify-center rounded-lg border text-[0.625rem] font-medium bg-white text-gray-400 border-gray-200 group-hover:border-indigo-600 group-hover:text-indigo-600"
							>W</span
						>
						<span class="truncate">Workcation</span>
					</a>
				</li>
			</ul>
		</li>
		<!-- Secondary column (hidden on smaller screens) -->
	</aside>
</div>
