<script>
    import { Column, Grid, RadioTile, Row, TileGroup } from "carbon-components-svelte";
    let key = "d"
</script>

<Grid>
    <Row>
      <Column>
        <h1>Test Tile</h1>
        <p>
          Test Para
        </p>
        <TileGroup legend="App switcher transitions" >
            <RadioTile value={key}>Tests</RadioTile>
        </TileGroup>
      </Column>
    </Row>
</Grid>