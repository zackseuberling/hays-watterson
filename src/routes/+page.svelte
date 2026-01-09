<script lang="ts">
	import { onMount } from "svelte";

  function shuffleArrayInPlace(array: Array<Array<string>>): Array<Array<string>> {
    let currentIndex = array.length
    let randomIndex;

    while (currentIndex !== 0) {
      randomIndex = Math.floor(Math.random() * currentIndex);
      currentIndex--;

      [array[currentIndex], array[randomIndex]] = [array[randomIndex], array[currentIndex]];
    }

    return array;
  }

  let colors = [
    ["#942248","#4257FA","#9CB3C2"],
    ["#942248","#B57D26","#CABDE5"],
    ["#942248","#FF6464","#4257FA"],
    ["#942248","#4257FA","#9CB3C2"],
    ["#7A1391","#B57D26","#9CB3C2"],
    ["#7A1391","#FF6464","#B57D26"],
    ["#7A1391","#4257FA","#CABDE5"],
    ["#FF6464","#B57D26","#CABDE5"],
    ["#7A1391","#FF6464","#CABDE5"],
  ];

  let randomColors = shuffleArrayInPlace(colors);

  onMount(() => {
    const htmlElement = document.documentElement;

    htmlElement.classList.add("opacity-100")
    htmlElement.style.setProperty("--color-1", randomColors[0][0])
    htmlElement.style.setProperty("--color-2", randomColors[0][1])
    htmlElement.style.setProperty("--color-3", randomColors[0][2])
  })
</script>

<svelte:head><title>Hays Watterson Memorial Scholarship</title></svelte:head>

<div class="relative w-full text-white overflow-clip">

<main class="relative">
  <div class="z-10 max-w-[1000px] mx-auto p-12 md:p-24 text-[28px] leading-[38px] relative">

  <header class="mb-8">
    <h1 class="text-center text-5xl leading-tight mb-4">Hays Watterson <br/> Memorial Scholarship</h1>
    <img src="/hays-watterson.jpeg" height="300" width="1000" class="aspect-5/3 object-cover block mx-auto" alt="" />
  </header>

  <p>Alexandra Hays and Brian Watterson were beloved members of our design community, and their impact in art, design, and education is deeply felt. To honor their memory, the <strong>Hays Watterson Memorial Scholarship</strong> endowment fund is being established at the Yale School of Art to help support talented graphic design students for years to come.</p>
  <p>The scholarship endowment is currently in the fundraising stage. Preliminary gifts totaling $35,000 have already been made but the endowment will not be secured until the fund reaches $50,000. If you are able, please help us reach our goal of $50,000 with a one-time gift or pledge that can be paid over 5 years.</p>

  <a href="https://secure.yale.imodules.com/s/1667/52/cart/form.aspx?sid=1667&gid=52&pgid=5594&cid=14277&bledit=1&dids=958.&origin=5767&_ga=2.21395512.26127765.1750777443-2035703091.1741025936" class="text-base text-center font-sans font-bold block sticky top-10 p-8 shadow-md hover:shadow-lg hover:bg-black/25 bg-black/15 backdrop-blur-xs cursor-pointer mx-16 rounded-full my-8 transition-all leading-0">Make a Donation</a>

  <section>
    <h2 class="text-center text-xl my-16">About Alexandra and Brian</h2>

    <p>Alexandra Hays and Brian Watterson met as graphic design MFA students at Yale, became life partners, and went on to flourishing design careers in the technology sector.</p>
    <p>Alexandra Hays (1984-2024) attended the Yale School of Art in 2010. Her artistic sensibility and special attention to the small joys of daily life enriched her professional activities that included gallery director, designer, and writer. Early in her career, she worked as an artist, asking fundamental questions about who is an artist, and what is art for. She later went on to work at Gladstone Gallery, then Google, where she excelled as a writer and project director.</p>
    <p>Brian Watterson (1984-2024) was a member of the Yale Graphic Design MFA Class of 2011. He was recognized in the design community as a devoted educator and for his remarkable aptitude in both graphic design and computer programming. In addition to his independent practice, he taught design at Parsons, was an early member of New York studio Linked by Air, and worked at Instagram as the lead designer of Threads.</p>
    <p>Alex and Brian were kind, talented, and generous individuals whose creativity radiated throughout all aspects of their shared life. Their integrity, spirit, and devotion to excellence in design brightened and inspired the lives of all who knew them.</p>
  </section>

  <section>
    <h2 class="text-center text-xl my-16">About the Scholarship</h2>

    <p>The Hays Watterson Memorial Scholarship is awarded annually to a second-year Yale MFA student in the graphic design department in memory of Alexandra Hays and Brian Watterson. This scholarship recognizes a talented designer who approaches technology with the kind of imagination and humanism that Alex and Brian brought to their life and work. The recipient is selected by a panel of full time faculty.</p>
    <p>This award is supported through a gift made by Alexandra and Brian’s families, friends, and colleagues. As an endowed fund, this scholarship will be awarded in perpetuity, with the potential over time to provide full tuition for a second-year graphic design student.</p>
  </section>

    <section>
    <h2 class="text-center text-xl my-16">If you have questions please contact <br/>
Nicole Freeman <a class="underline" href="mailto:nicole.freeman@yale.edu">nicole.freeman@yale.edu</a><br/>
😀</h2>
    </section>

  </div>
</main>

<footer class="relative z-10 p-12 w-full font-serif">
  <div class="flex w-full justify-between pb-36 uppercase">
    <a href="#top">&uparrow; Back to Top</a>
    <a href="https://secure.yale.imodules.com/s/1667/52/cart/form.aspx?sid=1667&gid=52&pgid=5594&cid=14277&bledit=1&dids=958.&origin=5767&_ga=2.21395512.26127765.1750777443-2035703091.1741025936">Donate</a>
    <a href="https://www.art.yale.edu/">Yale School of Art</a>
  </div>

  <div class="flex w-full justify-between font-bold text-2xl">
    <div>Yale School of Art <br/>Hays Watterson Memorial Scholarship</div>
    <img src="/6c1f28f2c8aed6c47c3f3d764557188482af31df.png" alt="Yale School of Art" width="92"/>
  </div>
</footer>


<div class="z-0 left-side absolute left-0 right-1/2 h-full inset-0"></div>
<div class="z-0 right-side absolute right-0 left-1/2 h-full inset-0"></div>
<div class="z-0 fixed inset-y-0 right-1/2 -mr-30 w-60 bg-transparent backdrop-blur-2xl"></div>
</div>

<style>
  .left-side {
    background: linear-gradient(-180deg, var(--color-1) 0%, var(--color-3) 84%);
  }

  .right-side {
    background: linear-gradient(-180deg, var(--color-2) 0%, var(--color-3) 84%);
  }
</style>
