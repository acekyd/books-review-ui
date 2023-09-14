<template>
  <header>
    <h1 class="text-3xl font-bold"> My Favorite Books</h1>

    <div class="wrapper">
      Sharing thoughts about books read.
      <p>My DID: did:ion:EiB81Zf...</p>
    </div>
  </header>

  <main class="content">
    <div class="full-reviews">
      <section class="existing-reviews">
        <h2>Reviews</h2>
        <div class="review">
          <div class="review-image">
            <img src="https://images-na.ssl-images-amazon.com/images/I/51UoqRAxwEL._SX331_BO1,204,203,200_.jpg" alt="Things fall apart (1958)" />
          </div>
          <div class="review-details">
            <div class="review-title">Things fall apart (1958)</div>
            <div class="review-author">User DID</div>
            <div class="review-rating">4.5 ⭐</div>
            <div class="review-comment">A classic novel with timeless themes and memorable characters. Fitzgerald's prose is simply enchanting.</div>
          </div>
          <div class="review-actions">
            <button class="btn btn-primary" @click="toggleReviewDetails">Edit</button>
            <button class="btn btn-danger">Delete</button>
          </div>
        </div>
        <div class="review">
          <div class="review-image">
            <img src="https://images-na.ssl-images-amazon.com/images/I/51UoqRAxwEL._SX331_BO1,204,203,200_.jpg" alt="Things fall apart (1958)" />
          </div>
          <div class="review-details">
            <div class="review-title">Things fall apart (1958)</div>
            <div class="review-author">User DID</div>
            <div class="review-rating">4.5 ⭐</div>
            <div class="review-comment">A classic novel with timeless themes and memorable characters. Fitzgerald's prose is simply enchanting.</div>
          </div>
          <div class="review-actions">
            <button class="btn btn-primary" @click="toggleReviewDetails">Edit</button>
            <button class="btn btn-danger">Delete</button>
          </div>
        </div>
        <div class="review">
          <div class="review-image">
            <img src="https://images-na.ssl-images-amazon.com/images/I/51UoqRAxwEL._SX331_BO1,204,203,200_.jpg" alt="Things fall apart (1958)" />
          </div>
          <div class="review-details">
            <div class="review-title">Things fall apart (1958)</div>
            <div class="review-author">User DID</div>
            <div class="review-rating">4.5 ⭐</div>
            <div class="review-comment">A classic novel with timeless themes and memorable characters. Fitzgerald's prose is simply enchanting.</div>
          </div>
          <div class="review-actions">
            <button class="btn btn-primary" @click="toggleReviewDetails">Edit</button>
            <button class="btn btn-danger">Delete</button>
          </div>
        </div>
      </section>
    </div>
    <div class="add-review">
        <section class="add-review">
          <h2>Add a Review</h2>
          <form id="review-form">
              <label class="block">
                <label for="book" class="block text-sm font-medium leading-6 text-gray-900">Book Title:</label>
                <input id="book" name="book" type="text" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
              </label>
              <label class="block">
                  <label for="book" class="block text-sm font-medium leading-6 text-gray-900">Book Author:</label>
                  <input id="book" name="author" type="text" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
                </label>
              <label class="block">
                <label for="rating" class="block text-sm font-medium leading-6 text-gray-900">Rating:</label>
                <select id="rating" name="rating" class="block w-full">
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
                <textarea id="comment" name="comment" rows="3" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"></textarea>
              </label>

              <button type="submit" class="btn btn-primary mt-4  w-full">Submit</button>
          </form>

        </section>
        <section class="edit-review">
          <h2>Edit Review</h2>
          <form id="review-form">
            <label class="block">
              <label for="book" class="block text-sm font-medium leading-6 text-gray-900">Book Title:</label>
              <input id="book" name="book" type="text" :value="editReviewDetails.title" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
            </label>
            <label class="block">
              <label for="book" class="block text-sm font-medium leading-6 text-gray-900">Book Author:</label>
              <input id="book" name="author" type="text" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
            </label>
            <label class="block">
              <label for="rating" class="block text-sm font-medium leading-6 text-gray-900">Rating:</label>
              <select id="rating" name="rating" class="block w-full">
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
              <textarea id="comment" name="comment" rows="3" class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"></textarea>
            </label>

            <button type="submit" class="btn btn-primary mt-4  w-full">Submit</button>
          </form>
        </section>
    </div>

  </main>
</template>

<script setup>
import { ref } from "vue";
import Books from "./assets/books.json";  // source: https://github.com/benoitvallon/100-best-books
const showReviewDetails = ref(false);
const editReviewDetails = ref({
  title: "Things fall apart (1958)",
  author: "Chinua Achebe",
  rating: "4.5",
  comment: "A classic novel with timeless themes and memorable characters. Fitzgerald's prose is simply enchanting."
})
console.log(Books);

const toggleReviewDetails = () => {
  showReviewDetails.value = !showReviewDetails.value;
}


</script>



<style scoped>
header {
  line-height: 1.5;
  background-color: #efefef;
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
  border-bottom: #ccc 1px solid;
  padding-bottom: 1em;
}

.review-image {
  margin-right: 1em;
}
.review-image img {
  width: 100px;
  height: auto;
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

.content {
  display: flex;
  flex-wrap: wrap;
}


  .full-reviews {
    flex:3;
    padding: 10px;
    border-right: #ccc 1px solid;
    padding-right: 20px;
    margin-top: 20px;
  }

  .add-review, .edit-review {
    flex: 2;
    padding: 10px;
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


}
</style>
