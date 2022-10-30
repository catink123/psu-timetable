<script lang="ts">
import TopAppBar, { Row, Section, Title } from '@smui/top-app-bar';
import IconButton from '@smui/icon-button';
import Tooltip, { Wrapper } from '@smui/tooltip';
import Card, { Content } from '@smui/card';

import TimetableView from './TimetableView.svelte';
</script>

<main>
  <TopAppBar variant="static">
    <Row>
      <Section>
        <IconButton class="material-icons">menu</IconButton>
        <Title>Timetable</Title>
      </Section>
      <Section align="end" toolbar>
        <Wrapper>
          <IconButton class="material-icons">edit</IconButton>
          <Tooltip>Edit current page</Tooltip>
        </Wrapper>
      </Section>
    </Row>
  </TopAppBar>
  <Card padded style="background-color: #AFA; margin: 5px;">
    Сейчас идёт зелёная неделя.
  </Card>
  <TimetableView></TimetableView>
</main>

<style>

</style>