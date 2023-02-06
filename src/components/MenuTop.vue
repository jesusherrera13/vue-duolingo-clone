<template>
    <n-menu v-model:value="activeKey" mode="horizontal" :options="menuOptions" />
</template>

<script>
import { defineComponent, h, ref } from "vue";
import { NIcon } from "naive-ui";
import {
  BookOutline as BookIcon,
  PersonOutline as PersonIcon,
  WineOutline as WineIcon,
  Flag as FlagIcon
} from "@vicons/ionicons5";

function renderIcon(icon) {
  return () => h(NIcon, null, { default: () => h(icon) });
}

const menuOptions = [
    {
        label: () => h(
            "a",
            {
                href: "https://www.duolingo.com/",
                target: "_blank",
                rel: "noopenner noreferrer"
            },
            "Duolingo"
        ),
        key: "hear-the-wind-sing",
        icon: renderIcon(BookIcon)
    },
    {
        label: "A Wild Sheep Chase",
        key: "a-wild-sheep-chase",
        // disabled: true,
        icon: renderIcon(BookIcon)
    },
    {
        label: null,
        key: "Dance Dance Dance",
        icon: renderIcon(BookIcon),
        children: [
            {
                label: "Francés",
                key: "frances",
                icon: renderIcon(FlagIcon)
                /* type: "group",
                label: "People",
                key: "people",
                children: [
                    {
                        label: "Narrator",
                        key: "narrator",
                        icon: renderIcon(PersonIcon)
                    },
                    {
                        label: "Sheep Man",
                        key: "sheep-man",
                        icon: renderIcon(PersonIcon)
                    }
                ] */
            },
            {
                label: "Inglés",
                key: "Inglés",
                icon: renderIcon(PersonIcon)
            },
        {
            label: "Beverage",
            key: "beverage",
            icon: renderIcon(WineIcon),
            children: [
            {
                label: "Whisky",
                key: "whisky"
            }
            ]
        },
        {
            label: "Food",
            key: "food",
            children: [
            {
                label: "Sandwich",
                key: "sandwich"
            }
            ]
        },
        {
            label: "The past increases. The future recedes.",
            key: "the-past-increases-the-future-recedes"
        }
        ]
    }
];

export default defineComponent({
  setup() {
    return {
      activeKey: ref(null),
      menuOptions
    };
  }
});
</script>