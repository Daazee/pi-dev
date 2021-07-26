<html>

<head>
    <title>HTML Tutorial</title>
    <script src="https://sdk.minepi.com/pi-sdk.js"></script>
    <script>
        Pi.init({ version: "2.0" })
        localStorage.setItem("ApiKey","ao9qeuduhwprqpthcgq4rk2rkbarfkgtqkibfftmdvbgatfitlztjiulqi1bxyld");
    </script>
    <!-- <script src="auth.js"></script> -->

    <script>
        function myFunction() {
            debugger;
            let amount = Number(document.getElementById("amount").value);
            let user = "deeprog";
            var api 
            Pi.createPaymentz({
                // Amount of π to be paid:
                amount: amount,
                // An explanation of the payment - will be shown to the user:
                memo: "...", // e.g: "Digital kitten #1234",
                // An arbitrary developer-provided metadata object - for your own usage:
                metadata: { /* ... */ }, // e.g: { kittenId: 1234 }
            }, {
                    // Callbacks you need to implement - read more about those in the detailed docs linked below:
                    onReadyForServerApproval: function (paymentId) { 
                        console.log("Approval => " + paymentId);
                     },
                    onReadyForServerCompletion: function (paymentId, txid) { 
                         console.log("Completion => " + paymentId);
                     },
                    onCancel: function (paymentId) {
                        console.log("Cancel =>" + paymentId)
                     },
                    onError: function (error, payment) { 
                         console.log("Error =>" + error + ";" + "Payment =>" + payment);
                     },
                });
        }
    </script>
</head>

<body>

    Amount: <input type="text" id="amount" name="amount" />
    <button id="btnRequest" onclick="myFunction()">Request for Payment</button>

</body>

</html>