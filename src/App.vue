<template>
  <Menu>
    <MenuButton>More</MenuButton>
    <MenuItems class="menu-items">
      <MenuItem v-slot="{ active }">
        <a :class='{ "bg-blue-500": active }' href="/account-settings">
          Account settings
          <span>icon</span>
        </a>
      </MenuItem>
      <MenuItem v-slot="{ active }">
        <a :class='{ "bg-blue-500": active }' href="/account-settings">
          Documentation
        </a>
      </MenuItem>
      <MenuItem v-slot="{ disabled }" disabled>
        <span :class='{ "bg-red-500": disabled }'>Invite a friend (coming soon!)</span>
      </MenuItem>
    </MenuItems>
  </Menu>

  <div>
    Some content here
  </div>

  <RadioGroup v-model="plan">
    <RadioGroupLabel>Plan</RadioGroupLabel>
    <RadioGroupOption v-slot="{ checked }" value="startup">
      <div :class="checked ? 'bg-blue-500' : ''">
        <div>Startup</div>
        <div>Details go here</div>
      </div>
    </RadioGroupOption>
    <RadioGroupOption v-slot="{ checked }" value="business">
      <span :class="checked ? 'bg-blue-500' : ''">Business</span>
    </RadioGroupOption>
    <RadioGroupOption v-slot="{ checked }" value="enterprise">
      <span :class="checked ? 'bg-blue-500' : ''">Enterprise</span>
    </RadioGroupOption>
  </RadioGroup>
</template>

<script>
import { Menu, MenuButton, MenuItems, MenuItem, RadioGroup,
    RadioGroupLabel,
    RadioGroupOption, } from "@headlessui/vue";

export default {
    components: {
      Menu,
      MenuButton,
      MenuItems,
      MenuItem,
      RadioGroup,
      RadioGroupLabel,
      RadioGroupOption,
    },
    data() {
      return {
        plan: '',
      }
    }
  };

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.bg-blue-500 {
  background: lightblue;
}

.menu-items {
  position: absolute;
  background: lightgray;
  display: flex;
  flex-direction: column;
}

.bg-red-500 {
  background: red;
}
</style>
