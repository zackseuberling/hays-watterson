<script>
  const setScroll = () => {
    const htmlElement = document.documentElement;
    const percentage = htmlElement.scrollTop / htmlElement.offsetHeight;

    htmlElement.style.setProperty("--scroll", Math.min(percentage * 100, 100).toString())
  }
</script>

<svelte:document onscroll={setScroll} onresize={setScroll} />

<div class="fixed w-1/2 inset-y-0 overflow-hidden bg-[rgba(121,252,69,1)]">
  <div class="left-side h-full w-dvw"></div>
</div>

<div class="fixed w-1/2 inset-y-0 right-0 overflow-hidden">
  <div class="left-0 absolute right-side h-full w-dvw bg-linear-to-r from-cyan-500  to-purple-900"></div>
</div>

<div class="fixed inset-y-0 right-1/2 -mr-8 w-16 bg-transparent backdrop-blur-sm"></div>
<div class="relative z-20 max-w-3xl mx-auto p-24">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras pellentesque fringilla justo, eu iaculis lacus auctor non. Vestibulum in aliquet felis, sit amet convallis leo. Proin at congue lorem, quis dignissim enim. Nulla viverra nisl sed eros faucibus, eget ultrices neque vestibulum. Vivamus sagittis gravida ex quis condimentum. Ut elementum lobortis ipsum nec posuere. Integer imperdiet fringilla libero vitae efficitur. Vivamus dapibus hendrerit lorem. Nam non dolor volutpat, condimentum odio eget, bibendum eros.</p>
  <p>Donec convallis mi id fringilla finibus. Duis et libero non est molestie rutrum. Duis at aliquet ligula. Integer non metus sit amet purus sollicitudin sodales. Maecenas sed ultricies lorem, at consequat urna. Praesent interdum non dolor aliquam volutpat. Etiam auctor bibendum lorem. Mauris aliquam orci ac turpis aliquet laoreet. Nullam faucibus eget dolor quis porta. In luctus nulla a nisi bibendum pharetra. Nunc condimentum tortor nec tincidunt venenatis. Donec placerat in nisl at volutpat. Donec interdum tincidunt nisi quis mattis.</p>
  <p>Proin fringilla nisl eros, mattis commodo ex semper ut. Morbi interdum leo a rutrum varius. Suspendisse commodo non nisl mollis pulvinar. Suspendisse ac efficitur mi, ac luctus dui. Vestibulum ex mauris, imperdiet quis neque nec, venenatis facilisis lorem. Phasellus scelerisque metus in purus convallis pharetra. Mauris hendrerit consectetur maximus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Mauris at dignissim ante, nec dignissim mauris. Suspendisse rhoncus dignissim metus vitae cursus. Morbi posuere turpis ut sem tincidunt maximus. Suspendisse lobortis felis vestibulum neque tempor sollicitudin. Curabitur sit amet faucibus lorem. Sed semper risus ut ex laoreet, scelerisque aliquet ligula interdum.</p>
  <p>Duis nec felis consectetur, accumsan nisl vitae, commodo turpis. Vestibulum venenatis, ipsum id aliquam gravida, arcu neque vehicula lacus, non porttitor tellus quam ut nibh. Quisque bibendum diam vel quam ornare lacinia. In sodales lobortis leo, vel ullamcorper leo convallis eget. Nunc venenatis purus massa, in vestibulum metus consectetur ac. Quisque vel justo mi. Praesent ac mauris vitae leo condimentum fringilla in nec urna. Vivamus laoreet gravida tincidunt. Duis id ultricies magna. Suspendisse ac neque est. Sed sagittis varius felis, quis pretium ante accumsan ut. Phasellus lobortis sem nec ipsum aliquam placerat. Vivamus tempus neque a mi interdum, nec aliquet eros dictum.</p>
  <p>Aliquam at eros in lacus ultrices tincidunt. Nunc auctor quis tortor sit amet blandit. Curabitur nec egestas ante. Aenean posuere dolor vel augue luctus mollis. Quisque convallis sit amet ante quis porta. Donec ornare eros eget erat auctor, in tristique libero iaculis. Vivamus id imperdiet quam. Cras ligula felis, rhoncus in tristique ac, finibus id lectus. Mauris vitae urna imperdiet, tempus lorem quis, commodo mauris. Sed ultrices lacinia justo, vitae rutrum ligula efficitur ac. Phasellus venenatis a nunc sit amet rhoncus. Vestibulum tincidunt velit consequat quam porttitor, id efficitur mi suscipit. Suspendisse potenti. Nulla facilisi. Nullam id mattis sapien. Curabitur et interdum arcu.</p>
</div>

<style>
  @reference "tailwindcss";
  p + p {
    @apply mt-8;
  }

  .left-side {
    background: #833AB4;
    background: linear-gradient(90deg,rgba(131, 58, 180, 1) 0%, rgba(253, 29, 29, 1) 35%, rgba(252, 205, 50, 1) 69%, rgba(121, 252, 69, 1) 100%);
    translate: calc(-1% * min(var(--scroll), 50)) 0;
  }
  .right-side {
    translate: calc(-1% * min(var(--scroll), 50)) 0;
  }

</style>
