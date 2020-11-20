<template>
  <div>
    <TheHeader />
    <!--  <BadgeList />
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    />
    <CourseGoals #default="slotProps">
      <h2>{{ slotProps.item }}</h2>
    </CourseGoals>
-->
    <button @click="setSelectedComponent('ActiveGoals')">Active Goal</button>
    <button @click="setSelectedComponent('ManageGoals')">Manage Goal</button>
    <!--
    <ActiveGoals v-if="selectedComponent === 'ActiveGoals'" />
    <ManageGoals v-if="selectedComponent === 'ManageGoals'" /> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from "./components/layout/TheHeader";
// import UserInfo from "./components/UserInfo";
// import BadgeList from "./components/BadgeList";
// import CourseGoals from "./components/CourseGoals";
import ActiveGoals from "./components/ActiveGoals";
import ManageGoals from "./components/ManageGoals";

export default {
  components: {
    TheHeader,
    // UserInfo,
    // BadgeList,
    // CourseGoals,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedComponent: "ActiveGoals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>