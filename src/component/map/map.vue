<template>
    <div>
        <search :layer="layer"></search>
        <tools></tools>
        <div id="map" class="big-map"></div>
    </div>
</template>
<style>
    .big-map{width:100%;height:100%;position: absolute;top:0;left:0;z-index: -1;}
</style>
<script lang="ts">
import Map from "./map";
export default Map;
</script>

        