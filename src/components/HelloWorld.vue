<template>
  <v-container class="text-center">
    <v-btn depressed color="primary" rounded outlined @click="getPDF"> Download Button. </v-btn>
  </v-container>
</template>

<script>
// import { jsPDF } from "jspdf";
import pdfMake from "pdfmake/build/pdfmake";
import pdfFonts from "pdfmake/build/vfs_fonts";
import { CVEQTM } from "../Images/imagesBase64";
import { SERIANU } from "../Images/imagesBase64";
import { MEGA_AFRICA } from "../Images/imagesBase64";
import { GAUGE_TWO } from "../Images/imagesBase64";
import { GAUGE_ONE } from "../Images/imagesBase64";
export default {
  name: "HelloWorld",

  data: () => ({}),
  methods: {
    getPDF() {
      // this.$store.dispatch("createPdf");
      pdfMake.vfs = pdfFonts.pdfMake.vfs;
      pdfMake.fonts = {
        Roboto: {
          normal: "Roboto-Regular.ttf",
          bold: "Roboto-Medium.ttf",
          italics: "Roboto-Italic.ttf",
          bolditalics: "Roboto-MediumItalic.ttf",
        },
        Bauhaus_Two: {
          normal: "Bauhaus-Two.ttf",
          bold: "Bauhaus-Two.ttf",
          italics: "Bauhaus-Two.ttf",
          bolditalics: "Bauhaus-Two.ttf",
        },
        PlayfairDisplay_Black: {
          normal: "PlayfairDisplay-Regular.ttf",
          bold: "PlayfairDisplay-Bold.ttf",
          italics: "PlayfairDisplay-Italic.ttf",
          bolditalics: "PlayfairDisplay-BoldItalic.ttf",
        },
        TheanoDidot: {
          normal: "TheanoDidot-Regular.ttf",
          bold: "TheanoDidot-Regular.ttf",
          italics: "TheanoDidot-Regular.ttf",
          bolditalics: "TheanoDidot-Regular.ttf",
        },
      };

      var tablesDefinition = {
        style: "tableExample",
        table: {
          widths: ["*", "*", "*", "*", "*", "*", "*", "*"],
          headerRows: 1,
          body: [
            [
              { text: "#", style: "tableHeader" },
              { text: "Ref", style: "tableHeader" },
              { text: "Practice", style: "tableHeader" },
              { text: "Existence Score", style: "tableHeader" },
              { text: "Completeness Score", style: "tableHeader" },
              { text: "Timeliness Score", style: "tableHeader" },
              { text: "Reporting Score", style: "tableHeader" },
              { text: "Score", style: "tableHeader" },
            ],
            ["1", "Sample ", "Sample value 3 Sample value 3", "50%", "50%", "50%", "50%", "50%"],
          ],
        },
        layout: "lightHorizontalLines",
      };

      var tableDefinitionTwo = {};
      tableDefinitionTwo["style"] = "tableExample";
      tableDefinitionTwo["layout"] = "lightHorizontalLines";
      tableDefinitionTwo["table"] = {};
      tableDefinitionTwo["table"]["widths"] = ["*", "*", "*", "*", "*", "*", "*", "*"];
      tableDefinitionTwo["table"]["headerRows"] = 1;
      tableDefinitionTwo["table"]["body"] = [];
      tableDefinitionTwo["table"]["body"][0] = [
        { text: "#", style: "tableHeader" },
        { text: "Ref", style: "tableHeader" },
        { text: "Practice", style: "tableHeader" },
        { text: "Existence Score", style: "tableHeader" },
        { text: "Completeness Score", style: "tableHeader" },
        { text: "Timeliness Score", style: "tableHeader" },
        { text: "Reporting Score", style: "tableHeader" },
        { text: "Score", style: "tableHeader" },
      ];
      tableDefinitionTwo["table"]["body"][1] = ["1", "Sample ", "Sample value 3 Sample value 3", "50%", "50%", "50%", "50%", "50%"];
      var docDefinition = {
        content: [
          [
            {
              columns: [
                {
                  width: 300,
                  columns: [
                    [
                      {
                        style: "header",
                        text: "\n Quarterly CVEQ Control Visibility Statement",
                      },
                      {
                        style: "cveq_description",
                        text: "\n The control visibility statement tracks and summarizes the overall effectiveness of implemented cyber security controls. The statement provides insights into an organisation’s ability to design and implement risk countermeasures that effectively and aggregately reduce the likelihood of a cyberrisk exposure.",
                      },
                    ],
                  ],
                },

                {
                  columns: [
                    [
                      {
                        style: "cveq_description_smaller",
                        text: "\n Organisation Name",
                      },
                      {
                        style: "cveq_description_smaller",
                        text: "Date Of The Year \n",
                      },

                      {
                        columns: [
                          {
                            width: "*",
                            text: "",
                          },
                          {
                            width: 90,
                            image: MEGA_AFRICA,
                          },
                        ],
                      },
                    ],
                  ],
                  // pageBreak: "after",
                },
              ],
            },
            {
              columns: [
                {
                  width: 300,
                  columns: [
                    [
                      {
                        style: "header2",
                        text: "\n CVEQ Control Effectiveness Level",
                      },
                      {
                        style: "header2_description",
                        text: "\n This gauge indicates the level of effectiveness and efficiency of implemented Cybersecurity controls in reducing an organisation Cyberrisk exposure level based on the control coverage, completeness and timeliness capabilities.",
                      },
                    ],
                  ],
                },

                {
                  columns: [
                    [
                      {
                        style: "header2_guage_description",
                        text: "The level of effectiveness ranges from 0 – 100. 0 – is low effectiveness while 100 is high effectiveness.",
                      },

                      {
                        style: "image_center",
                        width: 120,
                        image: GAUGE_ONE,
                      },
                    ],
                  ],
                  // pageBreak: "after",
                },
              ],
            },
            {
              style: "header3",
              text: "\n CVEQ Control Effectiveness Dashboard",
            },

            {
              style: "header3_description",
              text: "\n This dashboard indicates the level of effectiveness and efficiency of implemented Cybersecurity controls in reducing an organisation Cyberrisk exposure level based on the control coverage, completeness and timeliness capabilities. The control effectiveness level ranges from 0 – 100. 0 – means low effectiveness while 100 means high effectiveness",
              // pageBreak: "after",
            },
            {
              columns: [
                {
                  // width: 300,
                  columns: [
                    [
                      {
                        style: "header4",
                        text: "\n CVEQ Control Effectiveness Level",
                      },
                      {
                        style: "header4_description",
                        text: "\n This dashboard indicates the level of effectiveness and efficiency of implemented Cybersecurity controls in reducing an organisation Cyberrisk exposure level based on the control coverage, completeness and timeliness capabilities.",
                      },
                      {
                        style: "header4_description_bold",
                        text: "\n The control effectiveness level ranges from 0 – 100. 0 – means low effectiveness while 100 means high effectiveness",
                      },
                      {
                        style: "image_center",
                        width: 100,
                        image: GAUGE_ONE,
                      },
                    ],
                  ],
                },

                {
                  // width: 300,
                  columns: [
                    [
                      {
                        style: "header4",
                        text: "\n CVEQ Control Effectiveness Level",
                      },
                      {
                        style: "header4_description",
                        text: "\n This dashboard indicates the level of effectiveness and efficiency of implemented Cybersecurity controls in reducing an organisation Cyberrisk exposure level based on the control coverage, completeness and timeliness capabilities.",
                      },
                      {
                        style: "header4_description_bold",
                        text: "\n The control effectiveness level ranges from 0 – 100. 0 – means low effectiveness while 100 means high effectiveness",
                      },
                      {
                        text: "\n",
                      },
                      {
                        columns: [
                          {
                            style: "image_center",
                            width: 50,
                            image: GAUGE_TWO,
                          },
                          {
                            style: "tableExample",
                            table: {
                              widths: ["*", "*"],
                              headerRows: 1,
                              body: [
                                [
                                  { text: "SubDomain", style: "tableHeader", fillColor: "#fcdede" },
                                  { text: "Score", style: "tableHeader", fillColor: "#fcdede" },
                                ],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],
                              ],
                            },
                            layout: "lightHorizontalLines",
                          },
                        ],
                      },
                    ],
                  ],
                },

                {
                  // width: 300,
                  columns: [
                    [
                      {
                        style: "header4",
                        text: "\n CVEQ Control Effectiveness Level",
                      },
                      {
                        style: "header4_description",
                        text: "\n This dashboard indicates the level of effectiveness and efficiency of implemented Cybersecurity controls in reducing an organisation Cyberrisk exposure level based on the control coverage, completeness and timeliness capabilities.",
                      },
                      {
                        style: "header4_description_bold",
                        text: "\n The control effectiveness level ranges from 0 – 100. 0 – means low effectiveness while 100 means high effectiveness \n",
                      },
                      {
                        text: "\n",
                      },
                      {
                        columns: [
                          {
                            style: "image_center",
                            width: 50,
                            image: GAUGE_TWO,
                          },
                          {
                            style: "tableExample",
                            table: {
                              headerRows: 1,
                              widths: ["*", "*"],
                              body: [
                                [
                                  { text: "SubDomain", style: "tableHeader", fillColor: "#fcdede" },
                                  { text: "Score", style: "tableHeader", fillColor: "#fcdede" },
                                ],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],

                                [{ text: "SubDomain" }, { text: "Score" }],
                              ],
                            },
                            layout: "lightHorizontalLines",
                          },
                        ],
                      },
                    ],
                  ],
                  pageBreak: "after",
                },
              ],
            },
            "First paragraph tablesDefinition",
            tablesDefinition,
            tableDefinitionTwo,
          ],
        ],

        footer: function () {
          return {
            columns: [
              {
                margin: [20, 0, 0, 0],
                width: "auto",
                style: "cveq_footer_bold",
                text: "Disclaimer: ",
              },
              {
                margin: [0, 0, 20, 0],
                style: "cveq_footer",
                text: "CVEQ Dashboards and statements provide a more holistic, accurate and transparent view of your cyberrisk posture based on relevant static and real-time data for those parts of the organisation assessed or monitored by the Serianu.",
              },
            ],
          };
        },
        header: function () {
          return {
            margin: [5, 2, 10, 20],
            columns: [
              {
                width: 90,
                image: CVEQTM,
              },
              {
                width: "*",
                text: "",
              },
              {
                width: 90,
                image: SERIANU,
              },
            ],
          };
        },
        styles: {
          tableHeader: {
            bold: true,
            fontSize: 7,
            color: "black",
            font: "PlayfairDisplay_Black",
          },
          tableExample: {
            margin: [0, 5, 0, 15],
            fontSize: 7,
            font: "TheanoDidot",
            bold: true,
            alignment: "center",
          },
          image_center: {
            alignment: "center",
          },
          header: {
            fontSize: 12,
            bold: true,
            font: "PlayfairDisplay_Black",
            italics: false,
          },
          header2: {
            fontSize: 11,
            bold: true,
            font: "PlayfairDisplay_Black",
            italics: false,
          },
          header3: {
            fontSize: 10,
            bold: true,
            font: "PlayfairDisplay_Black",
            italics: false,
          },
          header3_description: {
            fontSize: 8,
            font: "TheanoDidot",
          },

          header4: {
            fontSize: 8,
            bold: true,
            font: "PlayfairDisplay_Black",
            italics: false,
          },
          header4_description: {
            fontSize: 7,
            font: "TheanoDidot",
          },
          header4_description_bold: {
            fontSize: 7,
            font: "PlayfairDisplay_Black",
            bold: true,
            italics: true,
          },
          header2_description: {
            fontSize: 9,
            font: "TheanoDidot",
          },
          cveq_description: {
            fontSize: 10,
            font: "TheanoDidot",
          },
          cveq_description_smaller: {
            fontSize: 8,
            font: "PlayfairDisplay_Black",
            bold: true,
            alignment: "right",
          },
          header2_guage_description: {
            fontSize: 7,
            font: "PlayfairDisplay_Black",
            bold: true,
            alignment: "center",
          },
          cveq_footer: {
            fontSize: 6,
            font: "PlayfairDisplay_Black",
          },
          cveq_footer_bold: {
            fontSize: 6,
            font: "PlayfairDisplay_Black",
            bold: true,
          },
        },
        defaultStyle: {
          // columnGap: 20,
        },
      };
      pdfMake.createPdf(docDefinition).open();
      pdfMake.createPdf(docDefinition).download();
    },
  },
};
</script>
