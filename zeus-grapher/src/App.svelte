<script lang="ts">
  
  import { state } from 'svelte'; 
  import Grapher from './Grapher.svelte'
  
  let numGraphers: number = 1;

  class grapher {
    
    readonly id: number;
    public lastUpdated: string;
    public name: string;
    public aspectRatio: {width: number, height: number};
    public scaleY: number;
    public scaleX: {start: number, end: number};
    public align: number;
    public highlightRange?: {start: number, end: number};
    public notes: string;
    public displaySeatVarience: boolean;
    public displayHrtfVarience: boolean;
    public displayHighlight: boolean;
    public displayNotes: boolean; 
    
    constructor(name: string, aspectRatio: {width: number, height: number}, scaleY: number, scaleX: {start: number, end: number}, align: number, notes: string, displaySeatVarience: boolean, displayHrtfVariance: boolean, displayHighlight: boolean, displayNotes: boolean, highlightRange?: {start: number, end:number}){
        this.id = numGraphers++;
        this.lastUpdated = new Date().toLocaleString();
        this.name = name;
        this.aspectRatio = aspectRatio;
        this.scaleX = scaleX;
        this.scaleY = scaleY;
        this.align = align;
        this.highlightRange = highlightRange;
        this.notes = notes;
        this.displaySeatVarience = displaySeatVarience;
        this.displayHrtfVarience = displayHrtfVariance;
        this.displayHighlight = displayHighlight;
        this.displayNotes = displayNotes;
    } 
  
  }

  let genericGraph: grapher = $state(new grapher("New graph", {width: 16, height: 9}, 20, {start: 20, end: 20000}, 1000, "", false, false, false, false))

</script>

<main>
  <Grapher {genericGraph}/>
</main>

<style>

</style>
