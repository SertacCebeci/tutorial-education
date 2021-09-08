<template>
  <div>
    <div class="flex justify-center p-10">
      <div>
        <div class="px-20 py-12 space-y-4 bg-gray-100 shadow-xl">
          <div>
            What is the power center of the unit cell?
            <div class="mt-2">
              <label class="inline-flex items-center">
                <input
                  type="radio"
                  class="form-radio"
                  name="accountType"
                  value="personal"
                />
                <span class="ml-2">Locoplast</span>
              </label>
              <label class="inline-flex items-center ml-6">
                <input
                  type="radio"
                  class="form-radio"
                  name="accountType"
                  value="busines"
                />
                <span class="ml-2">Mithocondria</span>
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