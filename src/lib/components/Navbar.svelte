<script lang="ts">
  // export let theme: 'dark' | 'light' = 'dark'; // Unused
</script>

<nav class="w-full bg-[#161617] text-[#cecece] text-xs font-normal">
  <div class="max-w-[1024px] mx-auto px-4 h-11 flex justify-between items-center">
    <!-- Apple Logo -->
    <a href="/" class="opacity-80 hover:opacity-100 transition-opacity px-2">
      <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 17 17" xmlns="http://www.w3.org/2000/svg">
        <path d="M15.5752 16.034C14.7336 17.266 13.7852 18.25 12.5684 18.25C11.4556 18.25 11.1204 17.594 9.8756 17.594C8.614 17.594 8.2468 18.234 7.234 18.25C5.9724 18.266 4.9068 17.134 4.0708 15.922C2.3652 13.45 1.07 9.682 2.8076 6.666C3.6684 5.17 5.2188 4.218 6.9068 4.218C8.1036 4.218 9.0708 5.034 9.8084 5.034C10.514 5.034 11.7268 4.09 13.1524 4.09C13.7252 4.09 15.3652 4.298 16.3652 5.762C16.2852 5.81 14.4652 6.874 14.4652 9.61C14.4652 12.874 17.2652 13.978 17.3324 14.01C17.2844 14.17 16.8684 15.634 16.3652 16.362L15.5752 16.034ZM11.422 4.202C12.0452 3.442 12.4372 2.394 12.3252 1.33C11.3324 1.37 10.1852 1.994 9.482 2.85C8.8908 3.53 8.4428 4.61 8.5868 5.65C9.6428 5.73 10.766 5.01 11.422 4.202Z" transform="translate(-2 -1)" />
      </svg>
    </a>

    <!-- Menu Items -->
    <ul class="hidden md:flex space-x-6 list-none">
      {#each ['Store', 'Mac', 'iPad', 'iPhone', 'Watch', 'Vision', 'AirPods', 'TV & Home', 'Entertainment', 'Accessories', 'Support'] as item}
        <li><a href="/" class="opacity-80 hover:opacity-100 transition-opacity tracking-tight">{item}</a></li>
      {/each}
    </ul>

    <!-- Mobile Menu Icon (Placeholder) -->
    <div class="md:hidden">
        <!-- Hamburger icon would go here -->
    </div>

    <div class="flex items-center space-x-4">
      <!-- Search -->
      <a href="/" class="opacity-80 hover:opacity-100 transition-opacity px-2">
        <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
           <path d="M15.504 13.616l-3.79-3.223c-0.392-0.353-0.811-0.514-1.149-0.499 0.895-1.048 1.435-2.407 1.435-3.893 0-3.314-2.686-6-6-6s-6 2.686-6 6 2.686 6 6 6c1.486 0 2.845-0.54 3.893-1.435-0.016 0.338 0.146 0.757 0.499 1.149l3.223 3.79c0.552 0.613 1.453 0.665 2.003 0.115s0.498-1.452-0.115-2.003zM6 10c-2.209 0-4-1.791-4-4s1.791-4 4-4 4 1.791 4 4-1.791 4-4 4z"></path>
        </svg>
      </a>

      <!-- Bag -->
      <a href="/" class="opacity-80 hover:opacity-100 transition-opacity px-2">
        <svg class="w-3.5 h-3.5 fill-current" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
           <path d="M11 3.5c0-1.93-1.57-3.5-3.5-3.5s-3.5 1.57-3.5 3.5h-2.5v12.5h12v-12.5h-2.5zM7.5 1c1.38 0 2.5 1.12 2.5 2.5h-5c0-1.38 1.12-2.5 2.5-2.5zM13 15h-10v-10.5h2v2.5c0 0.28 0.22 0.5 0.5 0.5s0.5-0.22 0.5-0.5v-2.5h4v2.5c0 0.28 0.22 0.5 0.5 0.5s0.5-0.22 0.5-0.5v-2.5h2v10.5z"></path>
        </svg>
      </a>
    </div>
  </div>
</nav>
