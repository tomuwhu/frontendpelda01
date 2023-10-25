<script>
  const n = 10, m = 12
  var [lr, lc, arr] = [Array(n).fill(0), Array(m).fill(0), {}]
</script>
<table>
  {#each lr as r, i}
    <tr>
      {#each lc as _, j}
        <td on:click={(e) => {
          if (arr[`${i}-${j}`])
            lr[i]--, lc[j]--, arr[`${i}-${j}`] = ''
          else
            lr[i]++, lc[j]++, arr[`${i}-${j}`] = 'h'
        }} class={arr[`${i}-${j}`]}></td>
      {/each}
      <td class="ro {r?'':'null'}">{r}</td>
    </tr>
  {/each}
  <tr>
    {#each lc as c, j}
      <td class="ro {c?'':'null'}">{c}</td>
    {/each}
  </tr>
</table>