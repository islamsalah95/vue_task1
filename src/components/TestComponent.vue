<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="printDiv">Print</button>
    <div ref="printContent" class="print-content">
      <p>
        This is the content of the printed div. 
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
         Corrupti harum, modi cupiditate, voluptatem deleniti explicabo aspernatur, 
         minus iusto esse exercitationem sed hic repellendus ipsam
         numquam rerum provident voluptates perspiciatis distinctio.

         Lorem ipsum dolor sit amet consectetur adipisicing elit.
         Corrupti harum, modi cupiditate, voluptatem deleniti explicabo aspernatur, 
         minus iusto esse exercitationem sed hic repellendus ipsam
         numquam rerum provident voluptates perspiciatis distinctio.

         Lorem ipsum dolor sit amet consectetur adipisicing elit.
         Corrupti harum, modi cupiditate, voluptatem deleniti explicabo aspernatur, 
         minus iusto esse exercitationem sed hic repellendus ipsam
         numquam rerum provident voluptates perspiciatis distinctio.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Vue Print Demo",
    };
  },
  methods: {
    printDiv() {
      const printContent = this.$refs.printContent;
      const printWindow = window.open("", "_blank");
      printWindow.document.write(`
        <html>
        <head>
          <title>print-2.pdf</title>
        </head>
        <body>
          ${printContent.outerHTML}
        </body>
        </html>
      `);
      printWindow.document.close();
      printWindow.print();
    },
  },
};
</script>

<style scoped>
.print-content {
  display: none;
}
</style>
