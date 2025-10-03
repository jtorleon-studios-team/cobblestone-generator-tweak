
# Cobblestone Generator Tweak

Tired of your cobblestone generator always giving the same block? This mod tweaks it so generators can produce various stone types and even rare ores.

## Default Generators

The mod comes with a set of ready-to-use generators so you can start right away without any configuration.

<table>
  <thead>
    <tr>
      <th>name</th>
      <th>file</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>cobblestone</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/cobblestone.json" target="_blank">cobblestone.json</a></td>
    </tr>
    <tr>
      <td>andesite</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/andesite.json" target="_blank">andesite.json</a></td>
    </tr>
    <tr>
      <td>diorite</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/diorite.json" target="_blank">diorite.json</a></td>
    </tr>
    <tr>
      <td>gravel</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/gravel.json" target="_blank">gravel.json</a></td>
    </tr>
    <tr>
      <td>sandstone</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/sandstone.json" target="_blank">sandstone.json</a></td>
    </tr>
    <tr>
      <td>stone</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/stone.json" target="_blank">stone.json</a></td>
    </tr>
    <tr>
      <td>mossy cobblestone</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/mossy_cobblestone.json" target="_blank">mossy_cobblestone.json</a></td>
    </tr>
    <tr>
      <td>coal ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/coal_ore.json" target="_blank">coal_ore.json</a></td>
    </tr>
    <tr>
      <td>deepslate coal ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/coal_ore_deepslate.json" target="_blank">coal_ore_deepslate.json</a></td>
    </tr>
    <tr>
      <td>copper ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/coal_ore.json" target="_blank">copper_ore.json</a></td>
    </tr>
    <tr>
      <td>deepslate copper ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/coal_ore_deepslate.json" target="_blank">copper_ore_deepslate.json</a></td>
    </tr>
    <tr>
      <td>lapis ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/lapis_ore.json" target="_blank">lapis_ore.json</a></td>
    </tr>
    <tr>
      <td>deepslate lapis ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/lapis_ore_deepslate.json" target="_blank">lapis_ore_deepslate.json</a></td>
    </tr>
    <tr>
      <td>redstone ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/redstone_ore.json" target="_blank">redstone_ore.json</a></td>
    </tr>
    <tr>
      <td>deepslate redstone ore</td>
      <td><a href="https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/blob/main/src/data/bettercobstgen/generator/redstone_ore_deepslate.json" target="_blank">redstone_ore_deepslate.json</a></td>
    </tr>
  </tbody>
</table>

## Creating Custom Generators with Datapacks

This mod is fully datapack-driven, which means you can add your own generators without touching the code.

1) Create a datapack in your datapacks/ folder.
2) Inside, add your JSON files under: `data/bettercobstgen/generator/<name>.json`
3) Define the block probabilities in your JSON. Example:
    ```json
    {
      "source_block_id": "minecraft:dirt",
      "generation_rules": [
        {
          "generated_block_id": "minecraft:dirt",
          "weight": 1.0 // 100%
        }
      ]
    }
    ```
    - Each generator rule must define a weight.
    - The sum of all weights for a given generator must not exceed 1.0.
    - If the total is higher, the datapack will be considered invalid and ignored.
4) Reload the datapack (/reload) and your new generator is instantly available.

This way, anyone can create and share custom generators easily, without writing a single line of Java.

You can find an example datapack at the following URL:
- [github.com/jtorleon-studios-team/cobblestone-generator-tweak/tree/main/example/compat_biome_o](https://github.com/jtorleon-studios-team/cobblestone-generator-tweak/tree/main/example/compat_biome_o)

## About Weight Rules

- Each generator rule must define a weight.
- The sum of all weights for a given generator must not exceed 1.0.
- If the total is higher, the datapack will be considered invalid and ignored.

Example
```json
{
  "source_block_id": "minecraft:dirt",
  "generation_rules": [
    {
      "generated_block_id": "minecraft:dirt",
      "weight": 0.5 // 50%
    },
    {
      "generated_block_id": "minecraft:sand",
      "weight": 0.5 // 50%
    }
  ]
}
```
```json
{
  "source_block_id": "minecraft:dirt",
  "generation_rules": [
    {
      "generated_block_id": "minecraft:dirt",
      "weight": 0.5 // 50%
    },
    {
      "generated_block_id": "minecraft:sand",
      "weight": 0.25 // 25%
    },
    {
      "generated_block_id": "minecraft:stone",
      "weight": 0.25 // 25%
    }
  ]
}
```
