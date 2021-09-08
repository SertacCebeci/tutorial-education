<template>
  <div>
    <div class="flex justify-center p-10">
      <div>
        <div class="px-20 py-12 space-y-4 bg-gray-100 shadow-xl">
          <div>
            Which one is grammatically correct?
            <div class="mt-2">
              <label class="inline-flex items-center">
                <input
                  type="radio"
                  class="form-radio"
                  name="accountType"
                  value="personal"
                />
                <span class="ml-2">Anyone can be the a hero.</span>
              </label>
              <label class="inline-flex items-center ml-6">
                <input
                  type="radio"
                  class="form-radio"
                  name="accountType"
                  value="busines"
                />
                <span class="ml-2">They is staying on the ground.</span>
              </label>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="justify-center flex items-center">
      <button
        class="
          bg-blue-500
          hover:bg-blue-700
          text-white
          font-bold
          py-2
          px-4
          rounded
          flex
          justify-center
          items-center
        "
      >
        See result
      </button>
    </div>
  </div>
</template>

<script>
</script>

<style>
</style>