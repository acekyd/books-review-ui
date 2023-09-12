<script setup>
import { ref } from "vue";
import Books from "./assets/books.json";  // source: https://github.com/benoitvallon/100-best-books
const showReviewDetails = ref(false);
console.log(Books);

const toggleReviewDetails = () => {
  showReviewDetails.value = !showReviewDetails.value;
}
</script>

<template>
  <header>
    <h1 class="text-3xl font-bold"> TBD Test Publishing</h1>

    <div class="wrapper">
      Discover historic books for your perusal. Leave a review after reading and on to the next.
    </div>
  </header>

  <main>
    <div class="flex-grid">
      <div class="col">
        <img src="https://raw.githubusercontent.com/benoitvallon/100-best-books/master/static/images/a-Dolls-house.jpg" alt="Book 1">
        Things Fall Apart (1958)
        <button class="btn btn-primary" @click="toggleReviewDetails">Reviews</button>
      </div>
      <div class="col">
        <img src="https://raw.githubusercontent.com/benoitvallon/100-best-books/master/static/images/a-Dolls-house.jpg" alt="Book 1">
        Book 2
        <button class="btn btn-primary" @click="toggleReviewDetails">Reviews</button>
      </div>
      <div class="col">
        <img src="https://raw.githubusercontent.com/benoitvallon/100-best-books/master/static/images/a-Dolls-house.jpg" alt="Book 1">
        Book 3
        <button class="btn btn-primary" @click="toggleReviewDetails">Reviews</button>
      </div>
    </div>
    <section class="book-details" v-show="showReviewDetails">
        <div class="book-info">
            <h2>Things Fall Apart (1958) Reviews</h2>
            <p>Author 1, Genre</p>
        </div>
        <hr />
        <section class="reviews">
            <div class="review">
              <div class="review-content">
                <p class="comment">This book is amazing!</p>
                <p class="rating">Rating: 4.5</p>
              </div>
              <div class="review-actions">
                <button class="btn btn-primary">Edit</button>
                <button class="btn btn-danger">Delete</button>
              </div>
            </div>
            <!-- Repeat for other reviews -->
        </section>
        <section class="add-review">
            <h2>Add a Review</h2>
            <form id="review-form">
                <label class="block">
                  <label for="rating" class="block text-sm font-medium leading-6 text-gray-900">Rating:</label>
                  <select id="rating" name="rating" class="block w-1/2">
                      <option value="1.0">1.0</option>
                      <option value="1.5">1.5</option>
                      <option value="2.0">2.0</option>
                      <option value="2.5">2.5</option>
                      <option value="3.0">3.0</option>
                      <option value="3.5">3.5</option>
                      <option value="4.0">4.0</option>
                      <option value="4.5">4.5</option>
                      <option value="5.0">5.0</option>
                  </select>
                </label>
                <label class="block">
                  <label for="comment" class="block text-sm font-medium leading-6 text-gray-900">Comment:</label>
                  <textarea id="comment" name="comment" rows="3" class="block w-1/2 rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"></textarea>
                </label>

                <button type="submit" class="btn btn-primary mt-4">Submit</button>

            </form>

        </section>
    </section>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  background-color: #ccc;
  text-align: center;
}

.btn {
  @apply py-2 px-4 text-white font-semibold rounded-lg shadow-md focus:outline-none focus:ring-2 focus:ring-opacity-75
}

.btn-primary {
  @apply bg-blue-500 hover:bg-blue-700 focus:ring-blue-400;
}

.btn-danger {
  @apply bg-red-500 hover:bg-red-700;
}

.reviews {
  margin-top: 1em;
}
.review {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1em;
}

.review-actions {
  display: flex;
  gap: 1em;
}

.review-form {
  margin: 1em;

}

.book-details {
  @apply border-2 border-gray-200 rounded-md p-4;
}

h2 {
  @apply text-2xl font-bold;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    flex-direction: column;
    place-items: center;
    padding: 20px calc(var(--section-gap) / 2);
    gap: 1em;
  }

  .col {
    padding: 0 1em;
    display: flex;
    flex-direction: column;
    gap: 1em;
    text-align: center;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .flex-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    margin: 20px 0;
  }
}
</style>
