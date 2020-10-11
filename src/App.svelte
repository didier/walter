<script>
  import Logo from './components/atoms/Logo.svelte'
  import { tap } from '@sveltejs/gestures'
  let current = 0
  let total = 8

  const drinkWater = () => {
    if (current < total) {
      current = current + 1
    }
  }
</script>

<header
  class="fixed w-screen px-8 py-8 grid gap-1 grid-flow-col-dense items-start justify-start">
  <Logo />
  <p class="font-semibold">Walter</p>
</header>
<main class="flex flex-col justify-center items-center h-screen w-screen">
  <h4>You've had</h4>
  <h1 class="mx-auto my-4 text-6xl px-8 text-center">{current}/{total}</h1>
  <h4>glasses of water today</h4>
</main>

<footer
  class="fixed bottom-0 left-0 w-screen px-8 py-8 flex items-center justify-center">
  <nav>
    <ul>
      <li>
        <button
          on:click={drinkWater}
          class="bg-teal-800 rounded-full -translate-y-32 inline-block p-6 shadow-xl transition-all duration-75 hover:bg-teal-700">
          <Logo />
        </button>
      </li>
    </ul>
  </nav>
</footer>
