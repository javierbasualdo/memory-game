<template>
  <UserGame v-if="!game.hasUser"/>
  <BoardGame v-else/>
  <EndGame v-if="game.endGame"/>
</template>

<script setup>
import { useMemoryGame } from '@/stores/game'
import useUser from '@/composables/useUser'
import UserGame from '@/components/UserGame.vue'
import BoardGame from '@/components/BoardGame.vue'
import EndGame from '@/components/EndGame.vue'

const game = useMemoryGame()
const { hasUser } = useUser()

hasUser()

</script>
