<template>
  <section>
    <div class="w-full self-center">
      <div class="flex justify-center flex-wrap pr-10 pl-10 pt-10">
        <template v-for="c in Props.contents">
          <a :href="'/blog/post/' + c.id ">
            <div class="w-72 h-96 bg-white m-2">
              <img :src="c.thumbnail.url" alt="" class="p-2 h-1/2 w-full object-cover" />
              <div class="p-2">
                <div class="text-center mt-3 mb-3 font-bold">
                  {{ c.title }}
                </div>
              </div>
            </div>
          </a>
        </template>
      </div>
      <div class="flex justify-center flex-wrap pr-10 pl-10">
        <div class="w-72 m-2 text-center ml-auto">
          <a
            href="/blog/"
            class="group relative inline-flex h-12 items-center justify-center overflow-hidden rounded-md bg-sky-500 px-6 font-medium text-neutral-200 transition hover:scale-110"
            ><span>記事一覧へ</span>
            <div
              class="absolute inset-0 flex h-full w-full justify-center [transform:skew(-12deg)_translateX(-100%)] group-hover:duration-1000 group-hover:[transform:skew(-12deg)_translateX(100%)]"
            >
              <div class="relative h-full w-8 bg-white/20"></div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
type Contents = {
  id: string;
  title: string;
  thumbnail: Object;
};

interface Props {
  contents: Contents;
}

const Props = withDefaults(defineProps<Props>(), {
  contents: {
    type: Object as () => Props,
    required: true,
  },
});
</script>
