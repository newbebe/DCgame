const KBank = require('@k-bank/sdk');
const kbank = KBank({
  mid: process.env.KBANK_MID,
  secretKey: process.env.KBANK_SECRET,
  sandbox: true          // 上线前改为 false
});

(async () => {
  const session = await kbank.checkouts.create({
    amount: 9900,        // 99 THB
    currency: 'THB',
    orderId: `dc-${Date.now()}`,
    paymentMethods: ['card', 'alipay', 'wechatpay', 'promptpay'],
    returnUrl: 'https://www.dingcheng.tech/success.html',
    cancelUrl: 'https://www.dingcheng.tech/cancel.html'
  });
  // 把 url 打印到 Actions 日志，前端轮询即可
  console.log('CHECKOUT_URL:', session.checkout_url);
})();
