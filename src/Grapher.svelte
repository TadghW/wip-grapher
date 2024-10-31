<script lang="ts">
    interface grapher {
        id: number;
        lastUpdated: string;
        name: string;
        aspectRatio: {width: number, height: number};
        scaleY: number;
        scaleX: {start: number, end: number};
        align: number;
        highlightRange?: {start: number, end: number};
        notes: string;
        displaySeatVarience: boolean;
        displayHrtfVarience: boolean;
        displayHighlight: boolean;
        displayNotes: boolean; 
    }

    let { thisGraph } = $props<{thisGrapher: grapher}>
</script>

GRAPHER 