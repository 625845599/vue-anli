<template>
  <div>
    <div class="header clearfix">
      <div id="main" class="header-left"></div>
      <div id="main2" class="header-left2"></div>
      <div id="main3" class="header-left3"></div>
      <div id="main7" class="header-left7"></div>
    </div>

    <div class="nav-mian clearfix">
      <div class="le clearfix">
        <span>今日金桔价格指数</span>
        <div id="main4" class="header-left4"></div>
        <div id="main5" class="header-left5"></div>
        <el-table :data="tableData" style="width: 100%" class="tabs">
          <el-table-column prop="date" label="品种"> </el-table-column>
          <el-table-column prop="name" label="报价区域"> </el-table-column>
          <el-table-column prop="address" label="现货价格"> </el-table-column>
          <el-table-column prop="price" label="批发价格"> </el-table-column>
          <el-table-column prop="prices" label="零售价格"> </el-table-column>
          <el-table-column prop="dates" label="报价时间"> </el-table-column>
        </el-table>
      </div>
      <div class="lg clearfix">
        <span>行业动态</span>
        <div id="main4" class="header-top">
          <el-table :data="tableDatas" stripe style="width: 100%">
            <el-table-column prop="datea" width="250"> </el-table-column>
            <el-table-column prop="namea" width="110"> </el-table-column>
            <el-table-column prop="addressa" width="100"> </el-table-column>
          </el-table>
        </div>
        <div id="main5" class="header-buttom" value>
          <el-radio-group v-model="tabPosition" style="margin-bottom: 30px">
            <el-radio-button label="微信指数"></el-radio-button>
            <el-radio-button label="微博指数" class="red"></el-radio-button>
            <el-radio-button label="百度指数"></el-radio-button>
          </el-radio-group>
          <div class="navs">
            <div class="lls">
              搜索指数
              <p class="el-icon-warning-outline"></p>
            </div>
            <div class="llr clearfix">
              <div>
                <i class="el-icon-mobile duibi">对比时间</i>
                <i>2021-05-11-2021-06-01</i>
              </div>
            </div>
            <div id="main6" class="header-left6"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as echarts from "echarts";
import "echarts-wordcloud";

export default {
  data() {
    return {
      tableData: [
        {
          date: "脆皮金桔",
          name: "广西-融安县",
          address: "2.20元/公斤",
          price: "3.20元/公斤",
          prices: "5.20元/公斤",
          dates: "2021-05-10",
        },
        {
          date: "脆皮金桔",
          name: "广西-融安县",
          address: "2.20元/公斤",
          price: "3.20元/公斤",
          prices: "5.20元/公斤",
          dates: "2021-05-10",
        },
        {
          date: "脆皮金桔",
          name: "广西-融安县",
          address: "2.20元/公斤",
          price: "3.20元/公斤",
          prices: "5.20元/公斤",
          dates: "2021-05-10",
        },
        {
          date: "脆皮金桔",
          name: "广西-融安县",
          address: "2.20元/公斤",
          price: "3.20元/公斤",
          prices: "5.20元/公斤",
          dates: "2021-05-10",
        },
      ],

      tableDatas: [
        {
          datea: "金桔与冰糖相遇创造出浓浓家乡味",
          namea: "来源:广西日报",
          addressa: "2021-05-10",
        },
        {
          datea: "金桔与冰糖相遇创造出浓浓家乡味",
          namea: "来源:广西日报",
          addressa: "2021-05-10",
        },
        {
          datea: "金桔与冰糖相遇创造出浓浓家乡味",
          namea: "来源:广西日报",
          addressa: "2021-05-10",
        },
        {
          datea: "金桔与冰糖相遇创造出浓浓家乡味",
          namea: "来源:广西日报",
          addressa: "2021-05-10",
        },
      ],
      tabPosition: "buttom",
    };
  },
  name: "Home",
  mounted() {
    var chartDom = document.getElementById("main");
    var myChart = echarts.init(chartDom);
    var option;

    var chartDom2 = document.getElementById("main2");
    var myChart2 = echarts.init(chartDom2);
    var option2;

    var chartDom3 = document.getElementById("main3");
    var myChart3 = echarts.init(chartDom3);
    var option3;

    var chartDom4 = document.getElementById("main4");
    var myChart4 = echarts.init(chartDom4);
    var option4;

    var chartDom5 = document.getElementById("main5");
    var myChart5 = echarts.init(chartDom5);
    var option5;

    var chartDom6 = document.getElementById("main6");
    var myChart6 = echarts.init(chartDom6);
    var option6;

    // var chart = echarts.init(document.getElementById("main7"));

    // 云图
    var Mychart = echarts.init(document.getElementById("main7"));
    var data1 = [
      { name: "融安金桔", value: 500 },
      { name: "深秋", value: 210 },
      { name: "止咳", value: 195 },
      { name: "化痰", value: 160 },
      { name: "初冬", value: 229 },
      { name: "柠檬", value: 60 },
      { name: "深秋", value: 210 },
      { name: "化痰", value: 120 },
      { name: "水果", value: 300 },
    ];
    var option = {
      // title: {
      //   text: "词云",

      //   textStyle: {
      //     color: "red",
      //   },
      //   offsetCenter: [0, "-50%"],
      // },
      // backgroundColor: "#000",
      series: [
        {
          type: "wordCloud",

          //网格尺寸,尺寸越大，字体之间的间隔越大
          grideSize: 20,

          //字体的最大与最小字号
          sizeRange: [12, 35],

          //字体旋转的范围
          rotationRange: [0, 20, 40, 60],

          //词云形状 circle:圆形,pentagon:五边形
          //cardioid:苹果形或心形,star:星形,diamond:钻石,
          //triangle-forward:三角形,triangle:三角形,smooth:平滑
          shape: "smooth",
          textStyle: {
            normal: {
              //字体随机颜色
              color: function () {
                return (
                  "rgb(" +
                  [
                    Math.round(Math.random() * 73),
                    Math.round(Math.random() * 173),
                    Math.round(Math.random() * 265),
                  ].join(",") +
                  ")"
                );
              },
            },
            emphasis: {
              //阴影距离
              shadowBlur: 1,

              //阴影颜色
              shadowColor: "#111",
            },
          },
          data: data1,
        },
      ],
    };
    Mychart.setOption(option);
    // 云图

    // 第一个图
    option = {
      series: [
        {
          type: "gauge",
          startAngle: 180,
          endAngle: 0,
          min: 0,
          max: 1,
          splitNumber: 8,
          axisLine: {
            lineStyle: {
              width: 10,
              color: [
                [0.25, "#FF6E76"],
                [0.5, "#FDDD60"],
                [0.75, "#58D9F9"],
                [1, "#7CFFB2"],
              ],
            },
          },
          pointer: {
            icon: "path://M12.8,0.7l12,40.1H0.7L12.8,0.7z",
            length: "10%",
            width: 6,
            offsetCenter: [0, "-55%"],
            itemStyle: {
              color: "auto",
            },
          },
          axisTick: {
            length: 10,
            lineStyle: {
              color: "auto",
              width: 2,
            },
          },
          splitLine: {
            length: 10,
            lineStyle: {
              color: "auto",
              width: 5,
            },
          },
          axisLabel: {
            color: "#464646",
            fontSize: 15,
            distance: -60,
            formatter: function (value) {
              if (value === 0.875) {
                return "乐观";
              } else if (value === 0.625) {
                return "积极";
              } else if (value === 0.375) {
                return "消极";
              } else if (value === 0.125) {
                return "悲观";
              }
            },
          },
          title: {
            offsetCenter: [0, "50%"],
            fontSize: 16,
          },
          detail: {
            fontSize: 40,
            offsetCenter: [0, "-20%"],
            valueAnimation: true,
            formatter: function (value) {
              return Math.round(value * 100);
            },
            color: "auto",
          },
          data: [
            {
              value: 0.7,
              name: "本月生产者信息指数",
            },
          ],
        },
      ],
    };
    option && myChart.setOption(option);
    // 第一个图

    // 第二个图
    option2 = {
      series: [
        {
          type: "gauge",
          startAngle: 180,
          endAngle: 0,
          min: 0,
          max: 1,
          splitNumber: 8,
          axisLine: {
            lineStyle: {
              width: 10,
              color: [
                [0.25, "#FF6E76"],
                [0.5, "#FDDD60"],
                [0.75, "#58D9F9"],
                [1, "#7CFFB2"],
              ],
            },
          },
          pointer: {
            icon: "path://M12.8,0.7l12,40.1H0.7L12.8,0.7z",
            length: "10%",
            width: 6,
            offsetCenter: [0, "-55%"],
            itemStyle: {
              color: "auto",
            },
          },
          axisTick: {
            length: 10,
            lineStyle: {
              color: "auto",
              width: 2,
            },
          },
          splitLine: {
            length: 10,
            lineStyle: {
              color: "auto",
              width: 5,
            },
          },
          axisLabel: {
            color: "#464646",
            fontSize: 15,
            distance: -60,
            formatter: function (value) {
              if (value === 0.875) {
                return "乐观";
              } else if (value === 0.625) {
                return "积极";
              } else if (value === 0.375) {
                return "消极";
              } else if (value === 0.125) {
                return "悲观";
              }
            },
          },
          title: {
            offsetCenter: [0, "50%"],
            fontSize: 16,
          },
          detail: {
            fontSize: 40,
            offsetCenter: [0, "-20%"],
            valueAnimation: true,
            formatter: function (value) {
              return Math.round(value * 100);
            },
            color: "auto",
          },
          data: [
            {
              value: 0.9,
              name: "上月生产者信息指数",
            },
          ],
        },
      ],
    };
    option2 && myChart2.setOption(option2);
    // 第二个图

    // 第三个图
    option3 = {
      tooltip: {
        trigger: "axis",
      },
      radar: [
        {
          indicator: [
            { text: "偏好指数", max: 100, color: "#8095d4" },
            { text: "风险指数", max: 100, color: "#8095d4" },
            { text: "热度指数", max: 100, color: "#8095d4" },
          ],
          center: ["50%", "45%"],
          radius: 80,
        },
      ],
      series: [
        {
          type: "radar",
          tooltip: {
            trigger: "item",
          },
          areaStyle: {},
          // title: {
          //   offsetCenter: [0, "50%"],
          //   fontSize: 16,
          // },
          data: [
            {
              value: [60, 73, 85, 40],
              name: "今日舆情指数",
            },
          ],
          label: {
            show: true,
            position: "top",
            // valueAnimation: true,
          },
        },
      ],
    };
    option3 && myChart3.setOption(option3);
    // 第三个图

    //第四个图
    var data = [];
    for (let i = 0; i < 5; ++i) {
      data.push(Math.round(Math.random() * 200));
    }
    option4 = {
      xAxis: {
        max: "dataMax",
      },
      yAxis: {
        type: "category",
        data: ["广西融安", "福建平安", "湖南四川", "广东深圳", "其他"],
        inverse: true,
        animationDuration: 300,
        animationDurationUpdate: 300,
        max: 4, // only the largest 3 bars will be displayed
      },
      series: [
        {
          realtimeSort: true,

          type: "bar",
          data: data,
          label: {
            show: true,
            position: "right",
            valueAnimation: true,
          },
        },
      ],
      legend: {
        show: true,
      },
      animationDuration: 10,
      animationDurationUpdate: 10,
      animationEasing: "linear",
      animationEasingUpdate: "linear",
    };
    option4 && myChart4.setOption(option4);
    //第四个图

    //第五个图
    option5 = {
      xAxis: {
        type: "category",
        data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
      },
      yAxis: {
        type: "value",
      },
      series: [
        {
          data: [820, 932, 901, 934, 4290, 2330, 5320],
          type: "line",
          smooth: true,
        },
      ],
    };

    option5 && myChart5.setOption(option5);
    //第五个图

    // 第六个图
    option6 = {
      xAxis: {
        type: "category",
        boundaryGap: false,
        data: [
          "2021-01-14",
          "2021-01-14",
          "2021-01-14",
          "2021-01-14",
          "2021-01-14",
          "2021-01-14",
          "2021-01-14",
        ],
      },
      yAxis: {
        type: "value",
      },
      series: [
        {
          data: [820, 932, 901, 934, 1290, 1330, 1320],
          type: "line",
          areaStyle: {},
        },
      ],
    };

    option6 && myChart6.setOption(option6);
    // 第六个图
  },

  components: {},
};
</script>

<style lang="less" scoped>
.header {
  width: 100%;
  height: 250px;
  display: flex;
  justify-content: flex-start;

  .header-left {
    width: 300px;
    height: 250px;
    // float: left;
    margin: 15px 20px 0px 10px;
  }
  .header-left2 {
    width: 300px;
    height: 250px;
    // float: left;
    margin: 15px 20px 0px 10px;
  }
  .header-left3 {
    width: 300px;
    height: 250px;
    // float: left;
    // margin-left: 150px;
    margin: 15px 20px 0px 10px;
    // margin-left: 100px;
  }
  .header-left7 {
    width: 300px;
    height: 250px;
    // float: left;
    // margin-left: 150px;
    margin: 0px 20px 0px 10px;
    // margin-left: 100px;
  }
}

.nav-mian {
  width: 1500px;
  height: 600px;
  margin-top: 15px;
  overflow: hidden;
  .le {
    float: left;
    // position: relative;
    width: 750px;
    height: 556px;
    border: 1px solid#eeeeee;
    border-radius: 10px;
    margin: 10px 5px 10px 50px;
    span {
      display: block;
      width: 120px;
      height: 25px;
      text-align: center;
      line-height: 25px;
      color: #fff;
      border-radius: 5px;
      background-color: #41d2cc;
    }
    .header-left4 {
      width: 350px;
      height: 300px;
      float: left;
      // position: absolute;
      // left: 20px;
      // top: 10;
      margin-left: 15px;
    }
    .header-left5 {
      width: 350px;
      height: 300px;
      float: right;
      // position: absolute;
      // left: 400px;
      // top: -120px;
    }
  }
  .lg {
    // position: relative;
    float: right;
    width: 620px;
    height: 556px;
    border: 1px solid#eeeeee;
    border-radius: 10px;
    margin: 10px 50px 10px 0px;
    overflow: hidden;
    span {
      display: block;
      width: 120px;
      height: 25px;
      text-align: center;
      line-height: 25px;
      color: #fff;
      border-radius: 5px;
      background-color: #41d2cc;
    }
    .header-top {
      width: 100%;
      height: 244px;
      border-bottom: 1px solid #f5f5f5;
      font-size: 10px;
      /deep/.el-table th {
        background-color: unset;
        // margin-bottom: 20px;
      }
    }
    .header-buttom {
      /deep/ .red {
        background-color: #41d0ca !important;
      }

      .navs {
        .lls {
          float: left;
          color: black;
          font-weight: 800;
          font-size: 13px;
          margin-left: 10px;
        }
        .llr {
          float: right;
          i {
            // display: inline-block;
            border-right: 1px solid #f5f5f5;
            margin-right: 25px;
            color: #706f6f;
          }
        }
        .header-left6 {
          width: 500px;
          height: 230px;
          font-size: 10px;
        }
      }
    }
  }
}
.clearfix::after {
  display: block;
  height: 0;
  content: "";
  clear: both;
  visibility: hidden;
}
/deep/.el-table th {
  background-color: #f5f5f5;
  margin-bottom: 20px;
}
</style>
