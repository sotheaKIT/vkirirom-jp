<template>
  <v-container>
    <section-title class="mt-7">デジタル開発サービス</section-title>
    <h2 class="subtitle pb-3">
      私たちは、企業が産業革命4.0を乗り切るため経営課題をグローバルチームで解決に導く戦略的開発パートナーです。
    </h2>
    <p class="text">
      A2Aデジタルジャパンは、日本企業が第4次産業革命にキャッチアップし、グローバルな市場で成長していくための戦略を共に実行する組織として設立されました。様々な業界を破壊するテクノロジーの登場により世界は混乱しています。A2Aデジタルジャパンの人的・技術的サービスを活用することで経営課題を解決しましょう。
    </p>
    <card-left-right
      v-for="(concept, id) in concepts"
      :key="id"
      :title="concept.title"
      :description="concept.description"
      :card-url="concept.goTo"
      :scroll-to="concept.scrollTo"
      :img-url="concept.imgSrc"
      btn-txt="続きを読む"
      :style="[
        id % 2 === 0
          ? { 'flex-direction': 'row-reverse', 'padding-left': '80px' }
          : { 'padding-right': '80px' },
        $vuetify.breakpoint.smAndDown
          ? { 'padding-left': 'unset', 'padding-right': 'unset' }
          : {}
      ]"
    />
    {{ concepts.title }}
  </v-container>
</template>

<script>
const SectionTitle = () => import("@/components/SectionTitle.vue");
const CardLeftRight = () => import("@/components/CardLeftRight.vue");
export default {
  name: "ConceptOne",
  components: { CardLeftRight, SectionTitle },
  data() {
    return {
      reverse: "flex-direction:row-revers;",
      concepts: [
        {
          title: "-業務理解力-<br />ビジネス経験豊富なマネジメント",
          description:
            "経営課題解決の真のパートナーとなるために、IT分野でのビジネス経験豊富なマネジメントチームを揃えています。",
          imgSrc: "images/concept/1.png",
          scrollTo: "#management"
        },
        {
          title: "-工数安定供給-<br />継続的エンジニア 養成・輩出の仕組み",
          description:
            "キリロム工科大学との連携、現地オフショア企業との連携、日本におけるエンジニアパートナーのネットワーク、アフターサポートを通して、継続的な人材リソースの確保が可能です。",
          imgSrc: "images/concept/2.png",
          scrollTo: "#flow"
        },
        {
          title: "-コストメリット-<br />グローバルなエンジニアを適正価格で",
          description:
            "カンボジアに拠点を置くことで、コストメリットを得ることができます。",
          imgSrc: "images/concept/3.png",
          goTo: "/about"
        }
      ]
    };
  }
};
</script>

<style lang="sass" scoped>
@import '~vuetify/src/styles/styles.sass'
.subtitle
  font-weight: bold
  font-size: 20px
  line-height: 24px
.text
  font-weight: 500
  font-size: 14px
  line-height: 17px
@media #{map-get($display-breakpoints, 'md-and-up')}
  .subtitle
    font-size: 20px
    line-height: 24px
  .text
    font-size: 18px
    line-height: 21px
</style>
