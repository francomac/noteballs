<template>
  <div class="notes">
    <div class="card has-background-success-dark p-4 mb-3">
      <div class="field">
        <label class="label">Message</label>
        <div class="control">
          <textarea class="textarea" placeholder="Textarea"></textarea>
        </div>
      </div>

      <div class="field is-grouped is-grouped-right">
        <div class="control">
          <button class="button is-link has-background-success">
            Add New Card
          </button>
        </div>
      </div>
    </div>

    <div class="card mb-3">
      <header class="card-header">
        <p class="card-header-title">Component</p>
        <button class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true"></i>
          </span>
        </button>
      </header>
      <div class="card-content">
        <div class="content">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Provident,
          totam? Enim, quo voluptates laborum totam, eaque, fugiat dolore ab
          inventore amet excepturi eligendi natus assumenda voluptas dolor?
          Perferendis, ipsam iure.
        </div>
      </div>
      <footer class="card-footer">
        <a href="#" class="card-footer-item">Edit</a>
        <a href="#" class="card-footer-item">Delete</a>
      </footer>
    </div>
  </div>
</template>
