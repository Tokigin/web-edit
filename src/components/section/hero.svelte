<script>
  import Icon from "../section/icon.svelte";
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
  <section class="bg-slate-800 w-2/12 text-center text-white">
    <h1 class="text-2xl p-5">Customize this web page</h1>
    <p class="text-xl p-1">Background Color</p>
    <div class="flex flex-wrap gap-1 justify-center">
      {#each bgcolors as color}
        <button
          class="{color} w-10 h-10 rounded-full"
          on:click={() => (bgcolor = color)}
        ></button>
      {/each}
    </div>
    <p class="text-xl p-1">Header Color</p>
    <div class="flex flex-wrap gap-1 justify-center">
      {#each bgcolors as color, i}
        <button
          class="{color} w-10 h-10 rounded-full"
          on:click={() => (headercolor = color)}
        ></button>
      {/each}
    </div>
    <p class="text-xl p-1">Header Text</p>
    <input type="text" class="text-black p-2 rounded" bind:value={logotext} />
    <div class="p-2">
      <button
        class="p-2 w-16 bg-slate-300 text-black rounded"
        on:click={() => {
          logoposition = "justify-start";
        }}>Left</button
      >
      <button
        class="p-2 w-16 bg-slate-300 text-black rounded"
        on:click={() => {
          logoposition = "justify-center";
        }}>Center</button
      >
      <button
        class="p-2 w-16 bg-slate-300 text-black rounded"
        on:click={() => {
          logoposition = "justify-end";
        }}>Right</button
      >
    </div>
    <p class="text-xl p-1">Choose Image</p>
    <div class=" flex flex-wrap gap-1 justify-center">
      {#each imgdir as img, i}
        <button
          class="p-2 w-10 bg-slate-300 text-black rounded"
          on:click={() => (defaultimg = img)}>{(i += 1)}</button
        >
      {/each}
    </div>
    <p class="text-xl p-1">Image Size</p>
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
    <p class="text-xl p-1">Banner Title</p>
    <input
      type="text"
      class="text-black p-2 rounded"
      bind:value={bannertitle}
    />
    <p class="text-xl p-1">Banner Description</p>
    <textarea
      type="text"
      class="text-black p-2 rounded w-64"
      bind:value={bannerdes}
    />
    <p class="text-xl p-1">Title Color</p>
    <div class="flex flex-wrap gap-1 justify-center">
      {#each textcolors as color, i}
        <button
          class="{bgcolors[i]} w-10 h-10 rounded-full"
          on:click={() => (defaulttitlecolor = color)}
        ></button>
      {/each}
    </div>
    <p class="text-xl p-1">Text Color</p>
    <div class="flex flex-wrap gap-1 justify-center">
      {#each textcolors as color, i}
        <button
          class="{bgcolors[i]} w-10 h-10 rounded-full"
          on:click={() => (defaulttextcolor = color)}
        ></button>
      {/each}
    </div>
    <p class="text-xl p-1">Number of Boxes</p>
    <button
      class="p-2 w-16 bg-slate-300 text-black rounded"
      on:click={() => {
        boxes++;
      }}>+</button
    >
    <button
      class="p-2 w-16 bg-slate-300 text-black rounded"
      on:click={() => {
        boxes--;
      }}>-</button
    >
  </section>
  <section class="w-10/12 {bgcolor} ">
    <div class="h-20 {headercolor} flex items-center {logoposition}">
      <h2 class="text-4xl {logocolor} px-5">{logotext}</h2>
    </div>
    <div class="flex p-10 gap-10">
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
      <p class="text-xl p-5">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit quo
        assumenda praesentium soluta accusamus
      </p>
      <div class="flex flex-wrap text-center px-10 justify-center gap-1">
        {#each { length: boxes } as _}
          <Icon title={defaulttitlecolor} text={defaulttextcolor}></Icon>
        {/each}
      </div>
    </section>
  </section>
</section>
