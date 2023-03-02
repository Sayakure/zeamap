<template>
  <!--  任务5.1-->
  <div>
    <div class="single-expression-viewer-content">
      <div class="top-container">
        <div class="info-help">
          <p>Browse Gene expressions among different tissues. The overview plot on the left shows the highest value of each tissues in the subdivision plot on the right.
          The gene expression data used here were from these researches:<br>
          - B73: <a href="https://science.sciencemag.org/content/353/6301/814">Walley J W, Sartor R C, Shen Z, <i>et al</i>. Integration of omic networks in a developmental atlas of maize[J]. Science, 2016, 353(6301): 814-818.</a><br>
          - SK: <a href="https://www.nature.com/articles/s41588-019-0427-6">Yang N, Liu J, Gao Q, <i>et al</i>. Genome assembly of a tropical maize inbred line provides insights into structural variation and crop improvement[J]. Nature genetics, 2019, 51(6): 1052.</a><br>
          To search for Maize Gene expression on more tissues/treatments, please visit <a href="http://bar.utoronto.ca/eplant_maize/">ePlant_maize</a> and <a href="https://qteller.maizegdb.org/">MaizeGDB</a>.
          </p>
        </div>
        <div class="search-container">
          <el-input
            v-model="expressionCode"
            class="search-input"
          ></el-input>
          <el-button class="search-button" @click="search">search</el-button>
        </div>
      </div>
    <div class="tissue-overview-content">
      <div class="svg-title">
        <h4 >Expression Tissue Overview</h4>
      </div>
      <div class="svg-viewer-data">
        <el-button @click="downloadTsv" class="download-TSV">download TSV</el-button>
        <img src='@/assets/images/zeamap.svg' />
      </div>
    </div>
  </div>
  </div>
</template>

<script>
import Title from "@/components/CommonComponents/Title.vue";
export default {
  name: "FirstTask",
  components: { Title },
  data() {
    return {
      expressionCode: "",
    };
  },
  methods: {
    downloadTsv() {
      // 请求下载
    },
    search() {
      // 发请求
      this.expressionCode = ""
    }
  }
};
</script>

<style lang="scss" scoped>
$mainColor: #28a745;
$deepMainColor: #19692C;
a {
  color: #28a745;
  &:hover {
    color: #19692C;
    text-decoration: underline;
  }
}
p {
  line-height: 26px;
  font-size: 16px;
  margin: 15px 0;
}
.single-expression-viewer-content {
  width: 90%;
  background: #fff;
  color: #222222;
  margin: 0 auto;
  border-radius: 3px;
  padding: 30px;
  .search-input {
    width: 30%;
    height: 38px;
    margin-right: 10px;
  }
}

.tissue-overview-content{
  background: #fff;
  margin: 20px auto;
  border-radius: 3px;
  .svg-title {
    h4 {
      font-weight: 600;
      font-size: 1.5rem;
    }
  }
}
.svg-viewer-data {
  width: 100%;
  border: 1px solid #EEEEEE;
  border-radius: 5px; 
  padding: 15px 10px;
  ::v-deep .download-TSV {
    border: 1px solid $mainColor;
    color: #fff;
    font-size: 16px;
    float: right;
    background-color: #74C687;
  }
}
::v-deep .el-input__inner {
  height: 38px;
  &:focus {
    border: 1px solid $mainColor;
    box-shadow: 5px 5px  20px #C9E9D0;
  }
}
::v-deep .search-button {
  background-color: $mainColor;
  color: #fff;
  &:hover {
    cursor: pointer;
  }
  &:active {
    border: 1px solid $mainColor;
    background-color: $deepMainColor;
    box-shadow: 0 0  20px #C9E9D0;
  }
}
</style>
