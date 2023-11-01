<script lang="ts">
	// import '../app.postcss';
	import type { PageData } from '../$types';
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
	import {
		DarkMode,
		Navbar,
		NavBrand,
		NavLi,
		NavUl,
		NavHamburger,
		Sidebar,
		SidebarGroup,
		SidebarItem,
		SidebarWrapper,
		Drawer,
		CloseButton,
		SidebarDropdownWrapper
	} from 'flowbite-svelte';
	import { Button, SidebarBrand, SidebarCta, SidebarDropdownItem } from 'flowbite-svelte';
    import { ChartPieSolid, ShoppingCartSolid, GridSolid, MailBoxSolid, UsersSolid, BagSolid, ArrowRightToBracketSolid, FileEditSolid } from 'flowbite-svelte-icons';
	import {UserSolid, FireSolid, BookSolid, WindowRestoreOutline, LifeBuoySolid } from 'flowbite-svelte-icons';
	import {  Avatar, Dropdown, DropdownItem, DropdownHeader, DropdownDivider } from 'flowbite-svelte';
    import { Search } from 'flowbite-svelte';
    import { SearchOutline } from 'flowbite-svelte-icons';
	import { Cog } from 'svelte-heros-v2';
	import { sineIn } from 'svelte/easing';

	let transitionParams = {
		x: -320,
		duration: 200,
		easing: sineIn
	};

	let breakPoint: number = 1024;
	let width: number;
	let backdrop: boolean = false;
	let activateClickOutside = true;
	let drawerHidden: boolean = false;
	$: if (width >= breakPoint) {
		drawerHidden = false;
		activateClickOutside = false;
	} else {
		drawerHidden = true;
		activateClickOutside = true;
	}
	onMount(() => {
		if (width >= breakPoint) {
			drawerHidden = false;
			activateClickOutside = false;
		} else {
			drawerHidden = true;
			activateClickOutside = true;
		}
	});
	const toggleSide = () => {
		if (width < breakPoint) {
			drawerHidden = !drawerHidden;
		}
	};
	const toggleDrawer = () => {
		drawerHidden = false;
	};
	$: activeUrl = $page.url.pathname;
	let spanClass = 'pl-2 self-center text-md text-gray-900 whitespace-nowrap dark:text-white';
	let divClass = 'w-full ml-auto lg:block lg:w-auto order-1 lg:order-none';
	let ulClass =
		'flex flex-col py-3 my-4 lg:flex-row lg:my-0 text-sm font-medium gap-4 dark:lg:bg-transparent lg:bg-white lg:border-0';
	let navDivClass =
		'bg-white dark:bg-gray-800 text-gray-500 dark:text-gray-400 border-gray-200 dark:border-gray-700 divide-gray-200 dark:divide-gray-700 flex items-center justify-between w-full mx-auto py-1.5 px-4';
</script>

<svelte:window bind:innerWidth={width} />
<header class="flex-none w-full mx-auto bg-white dark:bg-slate-950">
	<Navbar let:hidden let:toggle>
		<NavHamburger
			on:click={toggleDrawer}
			btnClass="focus:outline-none whitespace-normal rounded-lg focus:ring-2 p-1.5 focus:ring-gray-400 hover:bg-gray-100 dark:hover:bg-gray-600 m-0 mr-3 lg:hidden"
		/>
		<NavBrand href="/" class="lg:ml-64">
				<img src="images/logo-pelni.png" class="h-6 sm:h-9" alt="Pelni Logo" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white pl-4">
				Pelni
			</span>
		</NavBrand>
		<div class="flex items-center md:order-2">
			<Avatar id="avatar-menu" src="images/logo-pelni.png" />
		  </div>
		  <Dropdown placement="bottom" triggeredBy="#avatar-menu">
			<DropdownHeader>
			  <span class="block text-sm ">Regina Irene</span>
			  <span class="block truncate text-sm font-medium">regina@pelni.com</span>
			</DropdownHeader>
			<DropdownItem class='text-dark'>Dashboard</DropdownItem>
			<DropdownItem>Settings</DropdownItem>
			<DropdownDivider />
			<DropdownItem>Sign out</DropdownItem>
		  </Dropdown>      
		  <div class="ml-auto"> <!-- This is the new container for the search form -->
			<form class="flex gap-2 items-center">
			  <Search size="md" class="flex gap-2" placeholder="Search Barang Masuk, Tracking, Products..."></Search>
			  <Button size="sm">
				<SearchOutline class="w-5 h-5 mr-2 -ml-1" />
				Search
			  </Button>
			</form>
		  </div>
		<div class="flex items-center ml-auto">
			<DarkMode class="inline-block dark:hover:text-white hover:text-gray-900" />
		</div>
		<NavHamburger on:click={toggle} btnClass="lg:hidden" />
	</Navbar>
</header>

<Drawer
	transitionType="fly"
	{backdrop}
	{transitionParams}
	bind:hidden={drawerHidden}
	bind:activateClickOutside
	width="w-64"
	class="overflow-scroll pb-32"
	id="sidebar"
>
	<div class="flex items-center">
		<CloseButton on:click={() => (drawerHidden = true)} class="mb-4 dark:text-white lg:hidden" />
	</div>
	<Sidebar asideClass="w-54">
		<SidebarWrapper divClass="overflow-y-auto py-4 px-3 rounded dark:bg-gray-800">
			<SidebarGroup>
				<SidebarItem label="Dashboard" href="/" on:click={toggleSide} active={activeUrl === `/`} class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<ChartPieSolid
							class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Products" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<GridSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
					<svelte:fragment slot="subtext">
						<span
							class="inline-flex justify-center items-center px-2 ml-3 text-sm font-medium text-gray-800 bg-gray-200 rounded-full dark:bg-gray-700 dark:text-gray-300"
						>
							Pro
						</span>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Tracking" class='hover:text-blue-500' href="/">
					<svelte:fragment slot="icon">
						<MailBoxSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
					<svelte:fragment slot="subtext">
						<span
							class="inline-flex justify-center items-center p-3 ml-3 w-3 h-3 text-sm font-medium text-primary-600 bg-primary-200 rounded-full dark:bg-primary-900 dark:text-primary-200"
						>
							3
						</span>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Purchase Order" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<UserSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Barang Masuk" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<UserSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Barang Keluar" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<BagSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Sign Out" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<ArrowRightToBracketSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Sign In" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<FileEditSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
			</SidebarGroup>
			<SidebarGroup border>
				<SidebarItem label="Maintenance" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<FireSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Documentation" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<BookSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Testimoni" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<WindowRestoreOutline
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Help" class='hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<LifeBuoySolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
			</SidebarGroup>
		</SidebarWrapper>
	</Sidebar>
</Drawer>

<div class="flex px-4 mx-auto w-full">
	<main class="lg:ml-72 w-full mx-auto">
		<slot />
	</main>
</div>