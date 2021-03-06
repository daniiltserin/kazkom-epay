# Qazkom-epay
PHP library for Qazkom ePay integration

## Installation
```
$ composer require daniiltserin/qazkom-epay
```

## Basic usage
It is simple
```
$client = new \Epay\Client(array(
    'MERCHANT_CERTIFICATE_ID' => 'merchant certificate id',
    'MERCHANT_NAME'           => 'merchant name',
    'PRIVATE_KEY_FN'          => 'private key filename',
    'PRIVATE_KEY_PASS'        => 'private key password',
    'XML_TEMPLATE_FN'         => 'xml template filename',
    'XML_TEMPLATE_CONFIRM_FN' => 'xml confirmation template filename',
    'PUBLIC_KEY_FN'           => 'public key filename',
    'MERCHANT_ID'             => 'merchant id',
));

// Sign request for payment
$signature = $client->processRequest($orderId, $client->getCurrencyId('KZT'), $amount);

// Process payment system response
$result = $client->processResponse($response);

// Confirm request to unblock amount
$result = $client->processConfirmation($reference, $approvalCode, $orderId, $client->getCurrencyId('KZT'), $amount);
```

More information at https://testpay.kkb.kz/doc/htm/
