<script>
    import { Navbar, NavBrand, NavHamburger, Avatar, Dropdown, DropdownItem, DropdownHeader, DropdownDivider } from 'flowbite-svelte';
    import { Search, Button } from 'flowbite-svelte';
    import { SearchOutline } from 'flowbite-svelte-icons';
  </script>
  
  <Navbar class = "bg-indigo-800">
    <NavBrand href="/" style="margin-left: 40px;">
      <img src="images/logo-pelni.png" class="mr-3 h-6 sm:h-9" alt="Pelni Logo" />
      <span class="self-center whitespace-nowrap text-xl font-semibold"><h1 class="text-white dark:text-white">Pelni</h1></span>
    </NavBrand>    
    <div class="flex items-center md:order-2">
      <Avatar id="avatar-menu" src="images/logo-pelni.png" />
      <NavHamburger class1="w-full md:flex md:w-auto md:order-1" />
    </div>
    <Dropdown placement="bottom" triggeredBy="#avatar-menu">
      <DropdownHeader>
        <span class="block text-sm ">Regina Irene</span>
        <span class="block truncate text-sm font-medium">regina@pelni.com</span>
      </DropdownHeader>
      <DropdownItem class='text-white'>Dashboard</DropdownItem>
      <DropdownItem>Settings</DropdownItem>
      <DropdownDivider />
      <DropdownItem>Sign out</DropdownItem>
    </Dropdown>      
      <form class="flex gap-2">
        <Search size="md" class="flex gap-2 items-center" placeholder="Search Barang Masuk, Tracking, Products...">
        </Search>
        <Button size="sm">
          <SearchOutline class="w-5 h-5 mr-2 -ml-1" />
          Search
        </Button>
      </form>
  </Navbar>