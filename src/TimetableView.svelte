<script lang="ts">
import Accordion, { Content, Panel, Header } from '@smui-extra/accordion';
import DataTable, { Head, Cell, Body, Row } from '@smui/data-table';

interface TimetableDayData {
  name: string;
  disciplines: {
    time: string;
    name: string;
    description?: string;
  }[]
}

type TimetableData = TimetableDayData[];

let data: TimetableData = [
  {
    name: 'Понедельник',
    disciplines: [
      {
        time: '8:30 - 9:50',
        name: ''
      },
      {
        time: '10:05 - 11:25',
        name: 'л. Основы алгоритмизации и программирования',
        description: 'Оськин А.Ф. 12.09.-дискозал, с 19.09.-254В + 22ии,м'
      },
      {
        time: '11:40 - 13:00',
        name: 'л. Математическая анализ',
        description: 'Забелендик О.Н. 12.09.-дискозал, с 19.09.-252В'
      },
      {
        time: '13:30 - 14:50',
        name: 'л. Дискретная математика',
        description: 'Забелендик О.Н. 12.09.-дискозал, с 19.09.-252В'
      },
      {
        time: '15:05 - 16:25',
        name: 'Дискретная математика',
        description: 'Забелендик О.Н. 301Г'
      },
      {
        time: '16:40 - 18:00',
        name: ''
      }
    ]
  },
  {
    name: 'Вторник',
    disciplines: [
      {
        time: '8:30 - 9:50',
        name: 'ФИЗРА'
      },
      {
        time: '10:05 - sometime',
        name: 'ОПИ'
      }
    ]
  }
]
</script>

<Accordion>
    {#each data as day}
    <Panel>
        <Header>{day.name}</Header>
        <Content style="padding: 0">
            <DataTable style="width: 100%">
                <Head>
                <Row>
                    <Cell>Время</Cell>
                    <Cell style="width: 100%">Дисциплина</Cell>
                </Row>
                </Head>
                <Body>
                {#each day.disciplines as disc}
                    <Row>
                        <Cell>{disc.time}</Cell>
                        <Cell style="width: 100%">
                            <p>{disc.name}</p>
                            {#if disc.description}
                                <p>{disc.description}</p>
                            {/if}
                        </Cell>
                    </Row>
                {/each}
                </Body>
            </DataTable>
        </Content>
    </Panel>
    {/each}
</Accordion>