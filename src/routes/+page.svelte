<!-- Login Page -->
<script>
    import '../app.postcss';

    let email = '';
    let password = '';
  
    function handleSubmit() {
      // Handle the form submission here
      // You can send the data to a server or perform client-side validation
      console.log('Email:', email);
      console.log('Password:', password);
    }

    const handleClick = () => {
        window.location.href = '/dashboard'
    }
</script>

<div class="min-h-screen flex items-center justify-center relative">
    <div class="absolute top-0 left-0 w-full h-full bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1590496794008-383c8070b257?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1391&q=80');">
        <div class="bg-vignette w-full h-full absolute top-0 left-0"></div>
    </div>
    <div class="relative z-10 bg-opacity-80 backdrop-blur-md bg-gray-900 bg-blue p-6 rounded-lg shadow-md w-96">
        <div class="text-center flex flex-col items-center justify-center">
            <img src="images/logo-pelni.png" class="mb-4 max-w-full max-h-16" alt="Pelni Logo" />
            <h2 class="text-3xl font-semibold text-gray-200 mb-4">Login</h2>
        </div>                 
        <form on:submit={handleSubmit}>
            <div class="mb-4">
                <label for="email" class="block text-gray-300 text-sm">Email</label>
                <input type="email" id="email" bind:value={email} class="w-full px-4 py-2 border rounded-lg">
            </div>
            <div class="mb-4">
                <label for="password" class="block text-gray-300 text-sm">Password</label>
                <input type="password" id="password" bind:value={password} class="w-full px-4 py-2 border rounded-lg">
            </div>
            <div class="text-gray-300 flex justify-end">
                <p><a href="/">Lupa Password?</a></p>
            </div>
                <div class="flex items-center justify-between">
                    <!-- <a href="/sidebar"> -->
                        <button type="submit" class="mt-8 bg-blue-500 text-white px-2 py-2 rounded-lg hover:bg-blue-600 text-lg w-full" on:click={handleClick}>Login</button>
                      <!-- </a>                       -->
                </div>                
        </form>
        <div class="text-gray-300 mt-5 flex justify-center">
            <p>Belum punya akun? </p> <span style="color:aquamarine;"> <a href="/"> Daftar</a></span>
        </div>
    </div>
</div>

<style>
    .bg-vignette {
        background: radial-gradient(ellipse at center, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.6) 100%);
    }
</style>
