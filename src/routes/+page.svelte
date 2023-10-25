<script>
    const n = 10, m = 12
    var lr = Array(n).fill(0)
    var lc = Array(m).fill(0)
    var arr = Array(n).fill(0).map(v => Array(m))
</script>
<table>
    {#each lr as r, i}
        <tr>
            {#each lc as _, j}
                <td on:click={(e)=>{
                    arr[i][j] ? lr[i]-- : lr[i]++
                    arr[i][j] ? lc[j]-- : lc[j]++
                    arr[i][j] = arr[i][j] ? '' : 'h'
                }} class={arr[i][j]}>{i},{j}</td>
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