<script>
  import Icon from "../section/icon.svelte";
  import Banner1 from "./banner1.svelte";
  import Banner2 from "./banner2.svelte";
  import Banner3 from "./banner3.svelte";
  import Banner4 from "./banner4.svelte";

  let bgcolor = "bg-white";
  let headercolor = "bg-slate-600";
  let logocolor = "text-white";
  let logotext = "Lorem ipsum";
  let logoposition = "justify-start";
  let defaultimg = "/img/g1.jpg";
  let imgsize = 800;
  let bannertitle = "Lorem ipsum dolor sit amet";
  let bannerdes =
    "Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptates adipisci placeat porro magnam delectus commodi est eaque esse ducimus. Delectus, ullam. Soluta, fuga. Vitae obcaecati ad libero aut velit in!";
  let defaulttitlecolor = "text-black";
  let defaulttextcolor = "text-black";
  let boxes = 4;
  let heros = [1];
  let design = 1;
  const textcolors = [
    "text-white",
    "text-black",
    "text-slate-600",
    "text-stone-600",
    "text-red-600",
    "text-orange-600",
    "text-amber-600",
    "text-yellow-600",
    "text-lime-600",
    "text-emerald-600",
    "text-teal-600",
    "text-cyan-600",
    "text-sky-600",
    "text-blue-600",
    "text-indigo-600",
    "text-violet-600",
    "text-purple-600",
    "text-pink-600",
    "text-rose-600",
  ];
  const imgdir = ["/img/g1.jpg", "/img/g2.jpg", "/img/g3.jpg", "/img/g4.jpg"];
  const bgcolors = [
    "bg-white",
    "bg-black",
    "bg-slate-600",
    "bg-stone-600",
    "bg-red-600",
    "bg-orange-600",
    "bg-amber-600",
    "bg-yellow-600",
    "bg-lime-600",
    "bg-emerald-600",
    "bg-teal-600",
    "bg-cyan-600",
    "bg-sky-600",
    "bg-blue-600",
    "bg-indigo-600",
    "bg-violet-600",
    "bg-purple-600",
    "bg-pink-600",
    "bg-rose-600",
  ];
</script>

<section class="flex {defaulttextcolor}">
  <section class="w-2/12 text-center text-white bg-slate-800">
    <h1 class="p-5 text-2xl">Customize this web page</h1>
    <p class="p-1 text-xl">Background Color</p>
    <div class="flex flex-wrap justify-center gap-1">
      {#each bgcolors as color}
        <button
          class="{color} w-10 h-10 rounded-full"
          on:click={() => (bgcolor = color)}
        ></button>
      {/each}
    </div>
    <p class="p-1 text-xl">Header Color</p>
    <div class="flex flex-wrap justify-center gap-1">
      {#each bgcolors as color, i}
        <button
          class="{color} w-10 h-10 rounded-full"
          on:click={() => (headercolor = color)}
        ></button>
      {/each}
    </div>
    <p class="p-1 text-xl">Header Text</p>
    <input type="text" class="p-2 text-black rounded" bind:value={logotext} />
    <div class="p-2">
      <button
        class="w-16 p-2 text-black rounded bg-slate-300"
        on:click={() => {
          logoposition = "justify-start";
        }}>Left</button
      >
      <button
        class="w-16 p-2 text-black rounded bg-slate-300"
        on:click={() => {
          logoposition = "justify-center";
        }}>Center</button
      >
      <button
        class="w-16 p-2 text-black rounded bg-slate-300"
        on:click={() => {
          logoposition = "justify-end";
        }}>Right</button
      >
    </div>
    <p class="p-1 text-xl">Choose Image</p>
    <div class="flex flex-wrap justify-center gap-1">
      {#each imgdir as img, i}
        <button
          class="w-10 p-2 text-black rounded bg-slate-300"
          on:click={() => (defaultimg = img)}>{(i += 1)}</button
        >
      {/each}
    </div>
    <p class="p-1 text-xl">Image Size</p>
    <label class="text-black">
      <input
        class="w-16 p-1 rounded"
        type="number"
        bind:value={imgsize}
        min="500"
        max="2000"
      />
      <input type="range" bind:value={imgsize} min="500" max="2000" />
    </label>
    <p class="p-1 text-xl">Banner Title</p>
    <input
      type="text"
      class="p-2 text-black rounded"
      bind:value={bannertitle}
    />
    <p class="p-1 text-xl">Banner Description</p>
    <textarea
      type="text"
      class="w-64 p-2 text-black rounded"
      bind:value={bannerdes}
    />
    <p class="p-1 text-xl">Title Color</p>
    <div class="flex flex-wrap justify-center gap-1">
      {#each textcolors as color, i}
        <button
          class="{bgcolors[i]} w-10 h-10 rounded-full"
          on:click={() => (defaulttitlecolor = color)}
        ></button>
      {/each}
    </div>
    <p class="p-1 text-xl">Text Color</p>
    <div class="flex flex-wrap justify-center gap-1">
      {#each textcolors as color, i}
        <button
          class="{bgcolors[i]} w-10 h-10 rounded-full"
          on:click={() => (defaulttextcolor = color)}
        ></button>
      {/each}
    </div>
    <p class="p-1 text-xl">Number of Boxes</p>
    <button
      class="w-16 p-2 text-black rounded bg-slate-300"
      on:click={() => {
        boxes++;
      }}>+</button
    >
    <button
      class="w-16 p-2 text-black rounded bg-slate-300"
      on:click={() => {
        boxes--;
      }}>-</button
    >
    <p class="p-1 text-xl">Design</p>
    <div class="pb-2">
      <button
        class="w-16 p-2 text-black rounded bg-slate-300"
        on:click={() => {
          design++;
        }}>+</button
      >
      <button
        class="w-16 p-2 text-black rounded bg-slate-300"
        on:click={() => {
          design--;
        }}>-</button
      >
    </div>

    {#each { length: design } as _, i}
      <div class="p-2">
        <button
          class="w-16 p-2 text-black rounded bg-slate-300"
          on:click={() => {
            heros[i] = 1;
          }}>1</button
        >
        <button
          class="w-16 p-2 text-black rounded bg-slate-300"
          on:click={() => {
            heros[i] = 2;
          }}>2</button
        >
        <button
          class="w-16 p-2 text-black rounded bg-slate-300"
          on:click={() => {
            heros[i] = 3;
          }}>3</button
        >
        <button
          class="w-16 p-2 text-black rounded bg-slate-300"
          on:click={() => {
            heros[i] = 4;
          }}>4</button
        >
      </div>
    {/each}
  </section>
  <section class="w-10/12 {bgcolor} ">
    <div class="h-20 {headercolor} flex items-center {logoposition}">
      <h2 class="text-4xl {logocolor} px-5">{logotext}</h2>
    </div>
    <div class="flex gap-10 p-10">
      <div class="">
        <img width={imgsize} src={defaultimg} alt="img" />
      </div>
      <div>
        <h2 class="text-9xl p-5 {defaulttitlecolor}">{bannertitle}</h2>
        <p class="px-5 text-xl">{bannerdes}</p>
      </div>
    </div>
    <section class="text-center">
      <h2 class="text-5xl {defaulttitlecolor}">Lorem ipsum dolor sit amet</h2>
      <p class="p-5 text-xl">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit quo
        assumenda praesentium soluta accusamus
      </p>
      <div class="flex flex-wrap justify-center gap-1 px-10 text-center">
        {#each { length: boxes } as _}
          <Icon title={defaulttitlecolor} text={defaulttextcolor}></Icon>
        {/each}
      </div>
    </section>
    <section>
      {#each { length: design } as _, i}
        {#if heros[i] == 1}
          <Banner1 color={headercolor}></Banner1>
        {:else if heros[i] == 2}
          <Banner2 color={defaulttitlecolor}></Banner2>
        {:else if heros[i] == 3}
          <Banner3 color={defaulttitlecolor}></Banner3>
        {:else if heros[i] == 4}
          <Banner4 title={defaulttitlecolor} color={headercolor}></Banner4>
        {/if}
      {/each}
    </section>
  </section>
</section>
