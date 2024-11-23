Luma:
```xml
<?xml version="1.0"?>
<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
    <referenceContainer name="header-wrapper">
        <block class="Magento\Cms\Block\Block" name="footer_links_block">
            <arguments>
                <argument name="block_id" xsi:type="string">footer_links_block</argument>
            </arguments>
        </block>
    </referenceContainer>
</page>
```

Hyva


Register phtml
step1:
```
<?xml version="1.0"?>
<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
    <referenceContainer name="header-wrapper">
        <block class="Magento\Framework\View\Element\Template" name="custom_footer_links" template="Magento_Cms::footer.phtml"/>
    </referenceContainer>
</page>
```
step2:
```phtml
<?php
$cmsBlock = $block->getLayout()->createBlock(\Magento\Cms\Block\Block::class)
    ->setBlockId('footer_links_block')
    ->toHtml();
echo $cmsBlock;
?>
```

