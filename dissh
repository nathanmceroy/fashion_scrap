from bs4 import BeautifulSoup as bs
import requests
import lxml.html
import os
import math
import csv
import time


categories = ['accessories', 'clothing', 'beauty']
# , 'shoes', 'cosmetics', 'dresses', 'bottoms', 'tops', 'bodysuits', 'jackets-jumpers', 'swimwear', 'denim-shop', 'intimates', 'sets'

brands = []
titles = []
prices = []
variants = []
urls = []
dissh = []

os.chdir('../items')

def list_clean():
    for num in range(0, len(variants)):
        item = brands[num] , titles[num], prices[num], variants[num], urls[num]
        princess_polly.append(item)
        num += 1

def write_to_csv(brand, item):
    f = open(f'{brand}/princess_polly/{item}.csv', 'w')
    csv_wr = csv.writer(f)
    csv_wr.writerow(['Brand', 'Product title', 'color', 'Product price' , 'Product url', 'size 1', 'size 2', 'size 3', 'size 4', 'size 5', 'size 6', 'size 7', 'size 8', 'size 9', 'size 10', 'size 11', 'size 12', 'size 13', 'size 14', 'size 15', 'size 16', 'size 17', 'size 18'])
    return csv_wr

def web_page(url):
    header = {"User-Agent":'Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36'}
    page = requests.get(url, headers = header)
    soup = bs(page.content, 'lxml')
    return soup

def xpath_page(url):
    header = {"User-Agent":'Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36'}
    page = requests.get(url, headers = header)
    xpa = lxml.html.fromstring(page.content)
    return xpa       

# def grab_brand(url):
#     soup = web_page(url)
#     all_brands = soup.find_all(class_='product-brand')
#     if len(all_brands) >=1:
#         brand5 = str(all_brands).split('">')
#         brand4 = brand5[2].split('</a>')
#         brand3 = brand4[0]
#         brand = str(brand3.replace('amp;', ''))
#         brands.append(brand)
#     else:
#         brand = 'Princess Polly'
#         brands.append(brand)
    
    
# def grab_product_title(url):
#     soup = web_page(url)
#     all_titles = soup.find_all(class_='product-name')
#     for item in all_titles:
#         title1 = str(item.text)
#         title = title1.strip()
#         titles.append(title)

def grab_product_price(url):
    soup = web_page(url)
    price4 = soup.find(class_='price ng-binding')
    # price3 = str(price4).split('>')
    # price2 = price3[1].split('<')
    # price1 = price2[0]
    print(price4)
    # prices.append(price)

grab_product_price('https://dissh.com.au/collections/clothing')

# def colours_sizes(url):
#     xpa = xpath_page(url)
#     sizes = xpa.xpath('//*[@id="product-price-197150"]/span')
#     print(sizes)
#     # for item in alls:

# colours_sizes('https://www.princesspolly.com/carson-mini-dress')

# def grab_all_urls(url):
    soup = web_page(url)
    clothing_item = soup.find_all(class_='product-item__link')
    for item in clothing_item:
        url4 = str(item)
        url3 = url4.split('clothing/')
        url2 = url3[1].split('">')
        url1 = url2[0]
        url = f'https://dissh.com.au/{url1}'
        # # urls.append(url)
        print(url)
        print()
        print('-------------------------')
        print()

# grab_all_urls('https://dissh.com.au/collections/clothing')

# def item_num(category):
#     soup = web_page(f'https://dissh.com.au/collections/{category}')
#     num5 = soup.find(class_='ss-header-container')
#         # num4 = str(num5).strip()
#         # num3 = num4.split(' ')
#         # num2 = int(num4)
#         # num = int(num3)
#     #     return num
#     # except:
#     #     num = 1
#     #     return num
#     print(num5)
#     return num5

# item_num('clothing')

# for category in categories:
#     page_numbers = math.ceil(item_num(category)/24)
#     for num in range(1, 2):
#         print(category)
#         grab_all_urls(f'https://dissh.com.au/{category}?page={num}')


# for url in urls:
#     # grab_brand(url)
#     # grab_product_title(url)
#     # grab_product_price(url)
#     colours_sizes(url)
#     # print()
#     # print('-----------------')
#     # print()
#     time.sleep(1)
    

# def item_num(category):
#     try:
#         url = f'https://www.surfstitch.com/womens/{category}'
#         header = {"User-Agent":'Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.115 Safari/537.36'}
#         page = requests.get(url, headers=header)
#         soup = bs(page.content, 'lxml')
#         item_no5 = soup.find(class_='results-hits').text
#         item_no4 = str(item_no5)
#         item_no3 = item_no4.strip()
#         item_no2 = item_no3.split(' ')
#         item_no1 = item_no2[0]
#         if ',' in item_no1:
#             item_no = item_no1[0] + item_no1[2:]
#             item = int(item_no)
#             return item
#         else:
#             item = int(item_no1)
#             return item
#     except:
#         item = 0
#         return item     

# n = 1

# for category in categories:
#     item_count = item_num(category)
#     print(item_count)
#     for num in range(0, item_count, 20):
#         print(f'page number {n} of {math.ceil(item_count/20)}')
#         grab_brand(category, num)
#         grab_product_title(category, num)
#         grab_product_price(category, num)
#         grab_product_url(category, num)
#         n += 1
# i = 1
# for item in urls:
#     print()
#     print(f'item num {i} of {item_count}')
#     print()
#     grab_variants_from_urls(item)
#     i += 1

# print(brands)
# print(surf_stitch)
# print(len(surf_stitch))


# def create_new_folders():
#     b = set(brands)
#     print(b)
#     print(len(b))
#     for item in b:
#         try:
#             os.mkdir(item)
#             os.chdir(item)
#             os.mkdir('surf_stitch')
#             os.chdir('..')
#         except:
#             pass
    
# create_new_folders()

# list_clean()

# for item in surf_stitch:
#     try:
#         b = item[0]
#         t = item[1].replace(' ', '-')
#         write = write_to_csv(b, t)
#         for i in range(len(item[3])):
#             s = item[3][i][2]
#             print(item[3])
#             print(len(item[3]))
#             print(s)
#             print(len(s))
#             print('==================')
#             if len(s) == 1:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0]])
#             elif len(s) == 2:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1]])
#             elif len(s) == 3:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2]])
#             elif len(s) == 4:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3]])
#             elif len(s) == 5:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4]])
#             elif len(s) == 6:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5]])
#             elif len(s) == 7:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6]])
#             elif len(s) == 8:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7]])
#             elif len(s) == 9:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8]])
#             elif len(s) == 10:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9]])
#             elif len(s) == 11:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10]])
#             elif len(s) == 12:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11]])
#             elif len(s) == 13:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12]])
#             elif len(s) == 14:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12], item[3][i][2][13]])
#             elif len(s) == 15:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12], item[3][i][2][13], item[3][i][2][14]])
#             elif len(s) == 16:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12], item[3][i][2][13], item[3][i][2][14], item[3][i][2][15]])
#             elif len(s) == 17:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12], item[3][i][2][13], item[3][i][2][14], item[3][i][2][15], item[3][i][2][16]])
#             elif len(s) == 18:
#                 write.writerow([item[0], item[1], item[3][i][0], item[3][i][1], item[4], item[3][i][2][0], item[3][i][2][1], item[3][i][2][2], item[3][i][2][3], item[3][i][2][4], item[3][i][2][5], item[3][i][2][6], item[3][i][2][7], item[3][i][2][8], item[3][i][2][9], item[3][i][2][10], item[3][i][2][11], item[3][i][2][12], item[3][i][2][13], item[3][i][2][14], item[3][i][2][15], item[3][i][2][16], item[3][i][2][17]])
#             else:
#                 pass
#     except:
#         pass
