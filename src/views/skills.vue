<template>
    <v-expansion-panel expand v-model="panel" dark>
        <v-expansion-panel-content v-for="(skill,i) in skills" :key="i">
            <div slot="header">{{ skill.name }}</div>
            <v-data-table :headers="headers"
                          :items="skill.skills" hide-actions light
            Ò>
                <template slot="items" slot-scope="props">
                    <td>{{ props.item.tech }}</td>
                    <td>{{ props.item.years }}</td>
                    <td>{{ props.item.examples }}</td>
                </template>

            </v-data-table>
        </v-expansion-panel-content>
    </v-expansion-panel>
</template>

<script>
export default {
  name: "skills",
  data() {
    return {
      headers: [
        {
          text: "Technology",
          align: "left",
          value: "tech",
          width: "20%"
        },
        {
          text: "Years Experience",
          align: "left",
          value: "years",
          width: "20%"
        },
        {
          text: "Examples of where used",
          align: "left",
          value: "examples"
        }
      ],
      skills: [
        {
          name: "Java",
          skills: [
            {
              tech: "JSP - Java Server Pages",
              years: 5,
              examples: "Internet Banking"
            },
            {
              tech: "JSF - Java Server Faces",
              years: 5,
              examples: "Predefined messaging engine"
            }
          ]
        },
        {
          name: "Automation",
          skills: [
            {
              tech: "Chef",
              years: 2,
              examples:
                "Standard Bank Insurance Services, My Updates SMS transaction notification"
            }
          ]
        },
        {
          name: "Other programming languages",
          skills: [
            {
              tech: "HTML",
              years: 10,
              examples: "html, programming language??? yeah, I am sorry"
            },
            {
              tech: "Ruby",
              years: 2,
              examples: "Chef Recipes"
            },
            {
              tech: "Python",
              years: 1,
              examples: "Skynet KVM management"
            }
          ]
        }
      ],
      panel: [true, true, true]
    };
  }
};
</script>

<style scoped>
</style>
