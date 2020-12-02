[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

# BarCodeGenerator

Using Python Barcode Module I make a simple Barcode generator. It will automatically generate Barcode. 

    import barcode
    
# pip3 install python-barcode 

https://pypi.org/project/python-barcode/
    
    from barcode.writer import ImageWriter

""" Generate BarCode"""

    data1 = barcode.get_barcode_class('ean13')

# ean13 can only take digit

    data2 = barcode.get_barcode_class('code39')

# code39 can print string

# print_ = data1('2782923149212')

# print__ = data2('Sky 12')

# with writer it can convert file to PNG format . Without it it will print SVG format.

    print_ = data1('2782923149212', writer=ImageWriter())

    print__ = data2('Sky 12', writer=ImageWriter())

    get_data1 = print_.save('barcode ean13')
  
    get_data2 = print__.save('barcode code39')


""" Another Method """

from barcode import generate

    data3 = generate('isbn10', '7971483920457', output='barcode_svg')

# with file like object

    data4 = generate('isbn10', '5943234123275', writer=ImageWriter(), output='barcode_png')

print(data3, data4)
