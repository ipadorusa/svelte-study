<script>
  const menuList = [
    {menu:'Home', url:''},
    {menu:'Profile', url:''},
    {menu:'Article', url:''},
    {menu:'Article2', url:''},
  ]
</script>
<header id="header">
  <ul>
  {#each menuList as header}
    <li>{header.menu}</li>
  {/each}
  </ul>
</header>