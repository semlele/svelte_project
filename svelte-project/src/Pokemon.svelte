<script>
    import Bar from "./Bar.svelte";

    export let pokemon;

    const typeToClass = {
        'くさ':  'grass',
        'ほのお': 'fire',
        'みず': 'water'
    }

    let open = false;
    const toggle = () => open = !open;
</script>

<div class="pokemon {typeToClass[pokemon.type]}" on:click={toggle}>
    <h2>{pokemon.name}</h2>
    {#if open}
        <div class="stats">
            <h3>ステータス</h3>
            <Bar label="HP" value={pokemon.hp} />
            <Bar label="攻撃" value={pokemon.atk} />
            <Bar label="防御" value={pokemon.def} />
            <Bar label="特攻" value={pokemon.sAtk} />
            <Bar label="特防" value={pokemon.sDef} />
            <Bar label="素早" value={pokemon.spd} />
        </div>
    {:else}
        <div>クリックで詳細を見る</div>
    {/if}
</div>

<style>
    h2, h3 {font-weight: normal;}

    .pokemon {
        color: white;
        padding: 1em;
        cursor: pointer;
    }

    .grass {
        background-color: rgb(96, 184, 69);
    }

    .fire {
        background-color: rgb(226, 82, 82);
    }

    .water {
        background-color: rgb(62, 104, 240);
    }
</style>

