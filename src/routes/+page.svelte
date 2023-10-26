<script>
  const n = 7, m = 8
  var [lr, lc, tdd] = [Array(n).fill(0), Array(m).fill(0), {}]
</script>
<table>
  {#each lr as r, i}
    <tr>
      {#each lc as _, j}
        <td on:click={() => {
          if (tdd[`${i}-${j}`])
            lr[i]--, lc[j]--, tdd[`${i}-${j}`] = ''
          else
            lr[i]++, lc[j]++, tdd[`${i}-${j}`] = 'h'
        }} class={tdd[`${i}-${j}`]}></td>
      {/each}
      <td class="ro {r?'':'null'}">{r}</td>
    </tr>
  {/each}
  <tr>
    {#each lc as c, j}
      <td class="ro {c?'':'null'}">{c}</td>
    {/each}
    <td class="ro"></td>
  </tr>
</table>