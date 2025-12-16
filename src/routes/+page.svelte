<script lang="ts">
	import { onMount } from "svelte";

  function shuffleArrayInPlace(array: Array<string>): Array<string> {
    let currentIndex = array.length
    let randomIndex;

    while (currentIndex !== 0) {
      randomIndex = Math.floor(Math.random() * currentIndex);
      currentIndex--;

      [array[currentIndex], array[randomIndex]] = [array[randomIndex], array[currentIndex]];
    }

    return array;
  }

  let colors = ["#932147", "#FF6363", "#873983", "#9CB3C2", "#B57D26", "#4257FA"]
  let randomColors = shuffleArrayInPlace(colors).splice(0,5);

  onMount(() => {
    const htmlElement = document.documentElement;
    const height = htmlElement.offsetHeight;

    htmlElement.style.setProperty("--height", height.toString())
    htmlElement.style.setProperty("--color-1", randomColors[0])
    htmlElement.style.setProperty("--color-2", randomColors[1])
    htmlElement.style.setProperty("--color-3", randomColors[2])
    htmlElement.style.setProperty("--color-4", randomColors[3])
    htmlElement.style.setProperty("--color-5", randomColors[4])
  })
</script>



<div class="left-side set-height absolute left-0 right-1/2 h-dvh"></div>
<div class="right-side set-height absolute right-0 left-1/2 h-dvh"></div>

<div class="fixed inset-y-0 right-1/2 -mr-8 w-16 bg-transparent backdrop-blur-sm"></div>

<article class="relative z-20 max-w-4xl mx-auto p-24 text-2xl">
<h1 class="my-8">Hays Watterson Memorial Scholarship</h1>
<p>Alexandra Hays and Brian Watterson were beloved members of our design community, and their impact in art, design, and education is deeply felt. To honor their memory, the Hays Watterson Memorial Scholarship endowment fund is being established at the Yale School of Art to help support talented graphic design students for years to come.</p>
<p>The scholarship endowment is currently in the fundraising stage. Preliminary gifts totaling $35,000 have already been made but the endowment will not be secured until the fund reaches $50,000. If you are able, please help us reach our goal of $50,000 with a one-time gift or pledge that can be paid over 5 years.</p>

<section>
  <h2 class="my-8">About Alexandra and Brian</h2>

  <p>Alexandra Hays and Brian Watterson met as graphic design MFA students at Yale, became life partners, and went on to flourishing design careers in the technology sector.</p>
  <p>Alexandra Hays (1984-2024) attended the Yale School of Art in 2010. Her artistic sensibility and special attention to the small joys of daily life enriched her professional activities that included gallery director, designer, and writer. Early in her career, she worked as an artist, asking fundamental questions about who is an artist, and what is art for. She later went on to work at Gladstone Gallery, then Google, where she excelled as a writer and project director.</p>
  <p>Brian Watterson (1984-2024) was a member of the Yale Graphic Design MFA Class of 2011. He was recognized in the design community as a devoted educator and for his remarkable aptitude in both graphic design and computer programming. In addition to his independent practice, he taught design at Parsons, was an early member of New York studio Linked by Air, and worked at Instagram as the lead designer of Threads.</p>
  <p>Alex and Brian were kind, talented, and generous individuals whose creativity radiated throughout all aspects of their shared life. Their integrity, spirit, and devotion to excellence in design brightened and inspired the lives of all who knew them.</p>
</section>

<section>
  <h2 class="my-8">About the Scholarship</h2>

  <p>The Hays Watterson Memorial Scholarship is awarded annually to a second-year Yale MFA student in the graphic design department in memory of Alexandra Hays and Brian Watterson. This scholarship recognizes a talented designer who approaches technology with the kind of imagination and humanism that Alex and Brian brought to their life and work. The recipient is selected by a panel of full time faculty.</p>
  <p>This award is supported through a gift made by Alexandra and Brian’s families, friends, and colleagues. As an endowed fund, this scholarship will be awarded in perpetuity, with the potential over time to provide full tuition for a second-year graphic design student.</p>
</section>


</article>

<style>
  @reference "tailwindcss";
  p + p {
    @apply mt-8;
  }

  .set-height {
    height: calc(1px * var(--height));
  }

  .left-side {
    background: linear-gradient(-180deg, var(--color-1) 0%, var(--color-2) 37%, var(--color-2) 47%, var(--color-5) 84%);
  }

  .right-side {
    background: linear-gradient(-180deg, var(--color-3) 0%, var(--color-4) 37%, var(--color-4) 47%, var(--color-5) 84%);
  }
</style>
