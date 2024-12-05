<template>
    <v-container>
        <v-row>
            <v-col class="text-h2" align="center">
                Dashboard Overview
            </v-col>
        </v-row>
        <v-row>
            <!-- Loop through each column and assign cards dynamically -->
            <v-col
                v-for="(col, colIndex) in columns" 
                :key="colIndex"
                :cols="col.col"
                :sm="col.sm"
            >
                <!-- Loop through the cards that should be assigned to this column -->
                <v-card
                    v-for="(card, cardIndex) in getCardsForColumn(colIndex)" 
                    :key="cardIndex"
                    :text="card.card"
                >
                    <!-- Your card content here -->
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script setup>
import { ref } from 'vue';

const columns = ref([
    { col: '12' },
    { col: '12', sm: '4' },
    { col: '12', sm: '4' },
    { col: '12', sm: '4' },
]);

const cards = ref([
    { card: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nemo quos enim eligendi voluptatibus cum corporis numquam sit, nesciunt necessitatibus laborum debitis aperiam tempora iure suscipit praesentium amet dicta molestias. Quos assumenda nam cumque dolorum voluptate qui mollitia voluptas non debitis." },
    { card: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum, aperiam?" },
    { card: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum, aperiam?" },
    { card: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum, aperiam?" },
]);

// Helper function to get the cards for each column
const getCardsForColumn = (columnIndex) => {
    const cardsPerColumn = Math.ceil(cards.value.length / columns.value.length);
    const startIndex = columnIndex * cardsPerColumn;
    const endIndex = startIndex + cardsPerColumn;
    return cards.value.slice(startIndex, endIndex);
};

</script>
