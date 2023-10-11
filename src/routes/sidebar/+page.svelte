<script>
    import { Drawer, Button, CloseButton, Sidebar, SidebarBrand, SidebarCta, SidebarDropdownItem, SidebarDropdownWrapper, SidebarGroup, SidebarItem, SidebarWrapper } from 'flowbite-svelte';
    import { ChartPieSolid, ShoppingCartSolid, GridSolid, MailBoxSolid, UsersSolid, BagSolid, ArrowRightToBracketSolid, FileEditSolid } from 'flowbite-svelte-icons';
	import {UserSolid, FireSolid, BookSolid, WindowRestoreOutline, LifeBuoySolid } from 'flowbite-svelte-icons';
    import { sineIn } from 'svelte/easing';
    let hidden2 = true;
    let spanClass = 'flex-1 ml-3 whitespace-nowrap';
    let transitionParams = {
      x: -320,
      duration: 200,
      easing: sineIn
    };

	let isSidebarOpen = true; // Initial state of the sidebar

  function toggleSidebar() {
    isSidebarOpen = !isSidebarOpen;
  }
  </script>

<style>
	.sidebar {
	  width: 250px; /* Set your desired width */
	  transition: transform 0.3s ease-in-out;
	}
  
	.collapsed {
	  transform: translateX(-250px); /* Adjust the value to hide the sidebar */
	}

	/* CSS styles for the hamburger button */
.hamburger-button {
  background-color: #85b6d6; /* Set your desired background color */
  border: 1px solid #a0c2da; /* Set your desired border style and color */
  color: #fff; /* Set your desired text color */
  padding: 5px 10px; /* Set padding to adjust the button size */
  margin: 10px;
  border-radius: 4px; /* Set border-radius for rounded corners */
  cursor: pointer; /* Add a pointer cursor for user interaction */
  transition: background-color 0.3s ease; /* Add a smooth transition effect */
}

/* Hover effect (optional) */
.hamburger-button:hover {
  background-color: #4894c7; /* Set a different background color on hover */
}

  </style>
  
  <button class="hamburger-button icon {isSidebarOpen ? '' : 'icon-collapsed'}" on:click={toggleSidebar}>
	&#9776; <!-- Hamburger icon &#9776; -->
  </button>
  
  
  <div class="sidebar {isSidebarOpen ? '' : 'collapsed'}">
	<Sidebar class = "bg-indigo-800">
		<SidebarWrapper class = "bg-indigo-800">
			<SidebarGroup>
				<SidebarItem label="Dashboard" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<ChartPieSolid
							class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Products" class='text-white hover:text-blue-500' {spanClass}>
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
				<SidebarItem label="Tracking" class='text-white hover:text-blue-500' {spanClass} href="/form">
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
				<SidebarItem label="Barang Masuk" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<UserSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Barang Keluar" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<BagSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Sign In" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<ArrowRightToBracketSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Sign Out" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<FileEditSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
			</SidebarGroup>
			<SidebarGroup border>
				<SidebarItem label="Maintenance" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<FireSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Documentation" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<BookSolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Testimoni" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<WindowRestoreOutline
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
				<SidebarItem label="Help" class='text-white hover:text-blue-500'>
					<svelte:fragment slot="icon">
						<LifeBuoySolid
                        class="w-5 h-5 text-blue-500 transition duration-75 dark:text-blue-400 group-hover:text-blue-900 dark:group-hover:text-blue-900"
						/>
					</svelte:fragment>
				</SidebarItem>
			</SidebarGroup>
		</SidebarWrapper>
	</Sidebar>
</div>