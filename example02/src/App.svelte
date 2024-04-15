<script>
  let worker_form = {
    name: "",
    age: 0,
    profile: "",
    country: "",
    jobLocation: [],
    freeLancer: false,
    skills: [],
    yeaarsOfExperience: 0,
  };

  let submit_form = async (e) => {
    e.preventDefault(); // prevent page reload
    console.log(worker_form);
  };
</script>

<main>
  <h1>Worker Form</h1>
  <form on:submit={submit_form}>
    <div>
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" bind:value={worker_form.name} />
      </div>

      <div>
        <label for="age">Age</label>
        <input type="number" id="age" bind:value={worker_form.age} />
      </div>

      <div>
        <label for="profile">Profile</label>
        <textarea id="profile" bind:value={worker_form.profile} />
      </div>

      <div>
        <label for="country">Country</label>
        <select id="country" bind:value={worker_form.country}>
          <option value="Italy">Italy</option>
          <option value="France">France</option>
          <option value="Spain">Spain</option>
          <option value="Germany">Germany</option>
          >
        </select>
      </div>

      <div>
        <label for="job_location">Job Location</label>
        <select id="job_location" bind:value={worker_form.jobLocation} multiple>
          <option value="Italy">Italy</option>
          <option value="France">France</option>
          <option value="Spain">Spain</option>
          <option value="Germany">Germany</option>
          >
        </select>
      </div>

      <div>
        <label for="freelancer">Freelancer</label>
        <input type="checkbox" id="freelancer" bind:checked={worker_form.freelancer} />
      </div>

      <div>
        <label for="skills">Skills: </label>
        <input type="checkbox" id="html" bind:group={worker_form.skills} value="HTML" />
        <label for="html">HTML</label>
        <input type="checkbox" id="css" bind:group={worker_form.skills} value="CSS" />
        <label for="css">CSS</label>
        <input type="checkbox" id="js" bind:group={worker_form.skills} value="JavaScript" />
        <label for="js">JavaScript</label>
        <input type="checkbox" id="svelte" bind:group={worker_form.skills} value="Svelte" />
        <label for="svelte">Svelte</label>
      </div>

      <div>
        <label for="years_of_experience">Years of Experience</label>
        <input type="radio" id="0-2" bind:group={worker_form.yeaarsOfExperience} value="0-2" />
        <label for="0-2">0-2</label>
        <input type="radio" id="3-5" bind:group={worker_form.yeaarsOfExperience} value="3-5" />
        <label for="3-5">3-5</label>
        <input type="radio" id="6-10" bind:group={worker_form.yeaarsOfExperience} value="6-10" />
        <label for="6-10">6-10</label>
        <input type="radio" id="10+" bind:group={worker_form.yeaarsOfExperience} value="10+" />
        <label for="10+">10+</label>
      </div>
      <div>
        <button type="submit">Submit</button>
      </div>
    </div>
  </form>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    font-weight: 100;
  }

  h1 {
    color: firebrick;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  h2 {
    color: firebrick;
    text-transform: capitalize;
    font-size: 2.5em;
    font-weight: 50;
  }

  @media (min-width: 600px) {
    main {
      max-width: none;
    }
  }
</style>
