<script setup lang="ts">
import {
  ArrowRight,
  Eye,
  Heart,
  Info,
  Lock,
  MapPin,
  Moon,
  Sun,
  Target,
} from 'lucide-vue-next'
import { useDark, useToggle } from '@vueuse/core'
import { Button } from '@/components/ui/button'

const isDark = useDark()
const toggleDark = useToggle(isDark)

const missionText =
  'To empower members through accessible financial services, sustainable livelihood opportunities, and a strong culture of cooperation.'

const visionText =
  'A progressive and self-sustaining cooperative in Southwest Cebu where every member thrives, grows, and succeeds together.'
</script>

<template>
  <div
    id="top"
    class="flex min-h-svh flex-col bg-brand-cream text-foreground dark:bg-[#0f1412] dark:text-[#f2efe6]"
  >
    <div
      class="mx-auto flex w-full max-w-6xl flex-1 flex-col px-4 sm:px-6 lg:px-8 xl:max-w-7xl"
    >
      <div class="grid min-h-0 flex-1 grid-cols-1 lg:grid-cols-2">
        <!-- Left: hero -->
        <section
          class="relative flex flex-col border-b border-border/40 bg-brand-cream px-5 pb-10 pt-6 sm:px-8 sm:pb-12 sm:pt-8 md:items-center lg:items-stretch lg:border-b-0 lg:border-r dark:border-white/10 dark:bg-[#121a16]"
          aria-labelledby="hero-heading"
        >
          <div
            class="mb-8 flex w-full items-start justify-between gap-3 md:grid md:grid-cols-[1fr_auto_1fr] md:items-center md:gap-2 lg:flex lg:justify-between lg:gap-4"
          >
            <div
              class="hidden min-w-0 md:block lg:hidden"
              aria-hidden="true"
            />

            <a
              href="#top"
              class="group flex shrink-0 justify-self-center md:justify-self-center"
            >
              <img
                src="/padayon-logo-no-tagline.png"
                alt="Padayon Multipurpose Cooperative"
                width="360"
                height="360"
                class="h-28 w-auto shrink-0 object-contain sm:h-32 md:h-36 lg:h-40"
                decoding="async"
              >
              <span class="sr-only">Padayon Multipurpose Cooperative — home</span>
            </a>

            <div class="flex shrink-0 justify-end justify-self-end md:justify-self-end">
              <Button
                type="button"
                variant="outline"
                size="icon"
                class="size-10 rounded-full border-border bg-card/80 shadow-sm backdrop-blur-sm dark:border-white/15 dark:bg-white/5"
                :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'"
                @click="toggleDark()"
              >
                <Sun
                  v-if="!isDark"
                  class="size-5 text-brand-gold"
                  aria-hidden="true"
                />
                <Moon
                  v-else
                  class="size-5 text-brand-gold"
                  aria-hidden="true"
                />
              </Button>
            </div>
          </div>

          <div
            class="flex w-full flex-1 flex-col justify-center md:mx-auto md:max-w-xl md:items-center md:text-center lg:mx-0 lg:max-w-xl lg:items-start lg:pr-4 lg:text-left"
          >
            <h1
              id="hero-heading"
              class="text-balance font-serif text-4xl font-bold leading-[1.08] tracking-tight text-brand-forest sm:text-5xl lg:text-[2.75rem] xl:text-6xl dark:text-[#f2efe6]"
            >
              Padayon sa Kauswagan
            </h1>

            <p
              class="mt-4 max-w-2xl font-serif text-lg font-medium italic leading-snug tracking-[0.02em] text-brand-gold sm:text-xl md:text-2xl"
            >
              — Keep Moving Forward — Together
            </p>

            <p
              class="mt-5 max-w-md text-sm leading-relaxed text-muted-foreground sm:text-base md:mx-auto lg:mx-0"
            >
              A cooperative of people who keep moving forward — building a better Southwest Cebu, one member at a time.
            </p>

            <div class="mt-8 flex w-full justify-start md:justify-center lg:justify-start">
              <Button
                as="a"
                href="https://app.padamco.com"
                size="lg"
                class="h-12 gap-2 rounded-lg bg-brand-forest px-6 text-base font-semibold text-white hover:bg-brand-forest/90 dark:bg-[#2d6b52] dark:text-white dark:hover:bg-[#256047]"
              >
                <Lock
                  class="size-4 shrink-0"
                  aria-hidden="true"
                />
                Member Login
                <ArrowRight
                  class="ml-1 size-4 shrink-0 opacity-90"
                  aria-hidden="true"
                />
              </Button>
            </div>

            <p
              class="mt-6 flex max-w-md items-start gap-2 text-left text-xs text-muted-foreground sm:text-sm md:mx-auto md:justify-center lg:mx-0 lg:max-w-none lg:justify-start"
            >
              <Info
                class="mt-0.5 size-4 shrink-0 text-brand-gold"
                aria-hidden="true"
              />
              <span>Public services launching soon — members may log in above.</span>
            </p>
          </div>
        </section>

        <!-- Right: purpose -->
        <section
          class="flex flex-col justify-center bg-card px-5 py-10 sm:px-8 sm:py-12 lg:py-16 dark:bg-[#161c19]"
          aria-labelledby="purpose-heading"
        >
          <div class="mx-auto w-full max-w-lg">
            <p class="text-xs font-semibold uppercase tracking-[0.25em] text-brand-gold">
              Our purpose
            </p>
            <h2
              id="purpose-heading"
              class="mt-2 font-serif text-3xl font-bold tracking-tight text-brand-forest sm:text-4xl dark:text-[#f2efe6]"
            >
              Why we exist.
            </h2>

            <div class="mt-10 space-y-10">
              <div class="flex gap-4">
                <div
                  class="flex size-12 shrink-0 items-center justify-center rounded-full bg-brand-forest text-white dark:bg-[#2d6b52]"
                  aria-hidden="true"
                >
                  <Target class="size-5" />
                </div>
                <div>
                  <p class="text-xs font-semibold uppercase tracking-[0.2em] text-brand-gold">
                    Mission
                  </p>
                  <p class="mt-2 text-[15px] font-medium leading-relaxed text-brand-forest sm:text-base dark:text-[#e8e4dc]">
                    {{ missionText }}
                  </p>
                </div>
              </div>

              <div class="flex gap-4">
                <div
                  class="flex size-12 shrink-0 items-center justify-center rounded-full bg-brand-forest text-white dark:bg-[#2d6b52]"
                  aria-hidden="true"
                >
                  <Eye class="size-5" />
                </div>
                <div>
                  <p class="text-xs font-semibold uppercase tracking-[0.2em] text-brand-gold">
                    Vision
                  </p>
                  <p class="mt-2 text-[15px] font-medium leading-relaxed text-brand-forest sm:text-base dark:text-[#e8e4dc]">
                    {{ visionText }}
                  </p>
                </div>
              </div>
            </div>

            <div
              class="mt-10 flex w-full max-w-full items-start gap-2.5 rounded-2xl border border-brand-gold/40 bg-brand-cream/90 px-3.5 py-3 text-brand-forest shadow-sm sm:gap-3 sm:rounded-full sm:px-4 sm:py-2.5 dark:border-white/10 dark:bg-white/5 dark:text-[#e8dcc8]"
            >
              <Heart
                class="mt-0.5 size-4 shrink-0 text-brand-gold sm:mt-px"
                aria-hidden="true"
              />
              <p
                class="min-w-0 flex-1 text-pretty text-xs font-normal leading-relaxed text-brand-forest sm:text-sm sm:leading-snug dark:text-[#e8dcc8]"
              >
                Built on
                <strong class="font-semibold text-brand-forest dark:text-[#f2efe6]">Bayanihan</strong>, guided by
                <strong class="font-semibold text-brand-forest dark:text-[#f2efe6]">Integridad</strong>, driven by
                <strong class="font-semibold text-brand-forest dark:text-[#f2efe6]">Paglambo</strong>.
              </p>
            </div>
          </div>
        </section>
      </div>
    </div>

    <footer
      class="border-t border-black/10 bg-brand-forest px-5 py-5 text-sm text-white/95 sm:px-8 dark:border-white/10"
    >
      <div class="mx-auto flex max-w-6xl flex-col gap-4 px-4 sm:flex-row sm:items-center sm:justify-between sm:gap-6 sm:px-6 lg:px-8 xl:max-w-7xl">
        <p class="flex items-start gap-2 sm:items-center">
          <MapPin
            class="mt-0.5 size-4 shrink-0 text-brand-gold sm:mt-0"
            aria-hidden="true"
          />
          <span>Alegria, Cebu, Philippines 6030</span>
        </p>
        <p class="text-white/80 sm:text-right">
          © {{ new Date().getFullYear() }} Padayon Multipurpose Cooperative
        </p>
      </div>
    </footer>
  </div>
</template>
