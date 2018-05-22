# Weibo Scraper


![PyPI](https://img.shields.io/pypi/v/weibo-scraper.svg)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/weibo-scraper.svg)
[![Build Status](https://travis-ci.org/Xarrow/weibo-scraper.svg?branch=master)](https://travis-ci.org/Xarrow/weibo-scraper)
[![codecov](https://codecov.io/gh/Xarrow/weibo-scraper/branch/master/graph/badge.svg)](https://codecov.io/gh/Xarrow/weibo-scraper)
----

Simple weibo tweet scraper . Crawl weibo tweets by containedId without authorization.
There are many limitations in official API .
In general , we can inspect mobile site which has it's own API by Chrome.

----
# Installation

### pip

```shell

$ pip install weibo-scraper

```

Or Upgrade it.


```shell

$ pip install --upgrade weibo-scraper

```

### pipenv

```shell

$ pipenv install weibo-scraper

```
Or Upgrade it.

```shell
$ pipenv update --outdated # show packages which are outdated

$ pipenv update weibo-scraper # just update weibo-scraper

```




Only Python 3.6+ is supported

----
# Usage

1. You can get weibo tweets by containerid .

```python
>>> from weibo_scraper import  get_weibo_tweets
>>> for tweet in get_weibo_tweets(container_id='1076033637346297',pages=1):
>>>     print(tweet)
>>> ....

```

2. You  can also get weibo tweets by nick name which is exist . And the param of `pages` is optional .

```python
>>> from weibo_scraper import  get_weibo_tweets_by_name
>>> for tweet in get_weibo_tweets_by_name(name='Helixcs', pages=1):
>>>     print(tweet)
>>> ....
```

3. If you want to get all tweets , you can set the param of `pages` as `None`

```python
>>> from weibo_scraper import  get_weibo_tweets_by_name
>>> for tweet in get_weibo_tweets_by_name(name='Helixcs', pages=None):
>>>     print(tweet)
>>> ....
```

So you can get result which are formatted and ordered by create time  as below.

```json
{'card_type': 9, 'itemid': '1076031843242321_-_4241575901006618', 'scheme': 'https://m.weibo.cn/status/GhrzU4dRM?mblogid=GhrzU4dRM&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-20', 'id': '4241575901006618', 'idstr': '4241575901006618', 'mid': '4241575901006618', 'can_edit': False, 'text': '一个骚想法，可以利用travis来养爬虫<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_touxiao-3458a765a2.png" style="width:1em;height:1em;" alt="[偷笑]"></span> \u200b\u200b\u200b', 'textLength': 40, 'source': '微博 weibo.com', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 1, 'bid': 'GhrzU4dRM'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4241386402186993', 'scheme': 'https://m.weibo.cn/status/GhmEg9aW5?mblogid=GhmEg9aW5&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-19', 'id': '4241386402186993', 'idstr': '4241386402186993', 'mid': '4241386402186993', 'can_edit': False, 'text': '<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_chigua-90cb948c34.png" style="width:1em;height:1em;" alt="[吃瓜]"></span>', 'source': 'Weibo.intl', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'retweeted_status': {'created_at': '05-19', 'id': '4241354860553929', 'idstr': '4241354860553929', 'mid': '4241354860553929', 'can_edit': False, 'text': '<a class=\'k\' href=\'https://m.weibo.cn/p/searchall?containerid=231522type%3D1%26q%3D%23%E7%A8%8B%E5%BA%8F%E5%91%98%23%26t%3D10&luicode=10000011&lfid=1076031843242321\'>#程序员#</a>单步调试ing <a data-url="http://t.cn/R3TOZdD" href="https://m.weibo.cn/p/index?containerid=2304446f9cdaf295d5dd827b749295f6d04f40&url_type=39&object_type=video&pos=1&luicode=10000011&lfid=1076031843242321&ep=GhlPo2k6l%252C2093492691%252CGhlPo2k6l%252C2093492691" data-hide=""><span class="url-icon"><img src="https://h5.sinaimg.cn/upload/2015/09/25/3/timeline_card_small_video_default.png"></span></i><span class="surl-text">程序员的那些事的秒拍视频</a> \u200b\u200b\u200b', 'textLength': 39, 'source': '秒拍网页版', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 2093492691, 'screen_name': '程序员的那些事', 'profile_image_url': 'https://tva2.sinaimg.cn/crop.0.0.180.180.180/7cc829d3jw1e8qgp5bmzyj2050050aa8.jpg', 'profile_url': 'https://m.weibo.cn/u/2093492691?uid=2093492691&luicode=10000011&lfid=1076031843242321', 'statuses_count': 22503, 'verified': False, 'verified_type': 220, 'close_blue_v': False, 'description': '关注程序员相关话题；吐槽、投稿、合作、招聘请私信联系', 'gender': 'm', 'mbtype': 0, 'urank': 42, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 990653, 'follow_count': 371, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww2.sinaimg.cn/orj480/7cc829d3jw1e8qgp5bmzyj2050050aa8.jpg', 'like': False, 'like_me': False, 'badge': {'dzwbqlx_2016': 1, 'follow_whitelist_video': 1, 'user_name_certificate': 1}}, 'reposts_count': 46, 'comments_count': 15, 'attitudes_count': 60, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'weibo_position': 2, 'page_info': {'page_pic': {'url': 'https://wx1.sinaimg.cn/large/7cc829d3gy1frghz4u3y1j20dg0ag74v.jpg'}, 'page_url': 'https://m.weibo.cn/p/index?containerid=2304446f9cdaf295d5dd827b749295f6d04f40&url_type=39&object_type=video&pos=2&luicode=10000011&lfid=1076031843242321', 'page_title': '程序员的那些事的秒拍视频', 'content1': '程序员的那些事的秒拍视频', 'content2': '#程序员#单步调试ing', 'type': 'video', 'media_info': {'stream_url': 'https://f.us.sinaimg.cn/0015M2K2lx07kA4Rpk0U01040200113T0k010.mp4?label=mp4_ld&template=460x360.28&Expires=1526922411&ssig=iO39ZN98hI&KID=unistore,video'}, 'object_id': '1034:6f9cdaf295d5dd827b749295f6d04f40'}, 'bid': 'GhlPo2k6l'}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 3, 'obj_ext': '1万次观看', 'topic_struct': [{'title': '', 'topic_url': 'sinaweibo://searchall?containerid=231522&q=%23%E7%A8%8B%E5%BA%8F%E5%91%98%23', 'topic_title': '程序员', 'is_invalid': 0}], 'raw_text': '[吃瓜]', 'bid': 'GhmEg9aW5'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4241377967683238', 'scheme': 'https://m.weibo.cn/status/GhmqEweLc?mblogid=GhmqEweLc&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-19', 'id': '4241377967683238', 'idstr': '4241377967683238', 'mid': '4241377967683238', 'can_edit': False, 'text': '<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_chigua-90cb948c34.png" style="width:1em;height:1em;" alt="[吃瓜]"></span>//<a href=\'https://m.weibo.cn/n/谷大白话\'>@谷大白话</a>:￼//<a href=\'https://m.weibo.cn/n/重工组长于彦舒\'>@重工组长于彦舒</a>:……真是太惨了…………//<a href=\'https://m.weibo.cn/n/御景零\'>@御景零</a>://<a href=\'https://m.weibo.cn/n/-河豚豚-\'>@-河豚豚-</a>: 顿时我都不难过了。。。这他妈太惨了', 'source': 'Weibo.intl', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'pid': 4241342886237509, 'retweeted_status': {'created_at': '05-18', 'id': '4241154545078244', 'idstr': '4241154545078244', 'mid': '4241154545078244', 'can_edit': False, 'text': '多米诺骨牌爱好者的噩梦时刻。<a data-url="http://t.cn/R3jklU6" href="http://miaopai.com/show/dKC5AF-VVtYln1J9p~DsJjoB~q5YaogfR5AyRw__.htm?from=1110006030&weiboauthoruid=1560906700&showurl=http%3A%2F%2Fmiaopai.com%2Fshow%2FdKC5AF-VVtYln1J9p%7EDsJjoB%7Eq5YaogfR5AyRw__.htm%3Ffrom%3D1110006030%26weiboauthoruid%3D1560906700&url_open_direct=1&toolbar_hidden=1&url_type=39&object_type=video&pos=1&containerid=2304426adf59d8bc630fe31011111012d56b44&luicode=10000011&lfid=1076031843242321&ep=GhgCilj5a%252C1560906700%252CGhgCilj5a%252C1560906700" data-hide=""><span class="url-icon"><img src="https://h5.sinaimg.cn/upload/2015/09/25/3/timeline_card_small_video_default.png"></span></i><span class="surl-text">阑夕的秒拍视频</a> \u200b\u200b\u200b', 'textLength': 47, 'source': '微博 weibo.com', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1560906700, 'screen_name': '阑夕', 'profile_image_url': 'https://tva1.sinaimg.cn/crop.0.0.1597.1597.180/5d098bccgw1efpvdul7r7j218g18gndl.jpg', 'profile_url': 'https://m.weibo.cn/u/1560906700?uid=1560906700&luicode=10000011&lfid=1076031843242321', 'statuses_count': 13998, 'verified': True, 'verified_type': 0, 'verified_type_ext': 1, 'verified_reason': '逐鹿网（www.zhulu.com）创始人 微博签约自媒体', 'close_blue_v': False, 'description': '这个号好像又没有被禁言了。总之备用帐号是：weibo.com/visiondaily', 'gender': 'm', 'mbtype': 12, 'urank': 48, 'mbrank': 7, 'follow_me': False, 'following': False, 'followers_count': 797043, 'follow_count': 719, 'cover_image_phone': 'https://tva4.sinaimg.cn/crop.0.0.640.640.640/6ce2240djw1e8ystazttlj20hs0hsq4k.jpg', 'avatar_hd': 'https://ww1.sinaimg.cn/orj480/5d098bccgw1efpvdul7r7j218g18gndl.jpg', 'like': False, 'like_me': False, 'badge': {'anniversary': 1, 'bind_taobao': 1, 'vip_activity2': 1, 'self_media': 1, 'dzwbqlx_2016': 1, 'follow_whitelist_video': 1, 'user_name_certificate': 1, 'wenchuan_10th': 1}}, 'reposts_count': 17976, 'comments_count': 1491, 'attitudes_count': 8115, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'cardid': 'star_140', 'content_auth': 0, 'edit_config': {'edited': False}, 'weibo_position': 2, 'page_info': {'page_pic': {'url': 'http://imgaliyuncdn.miaopai.com/stream/dKC5AF-VVtYln1J9p~DsJjoB~q5YaogfR5AyRw___32768.jpg'}, 'page_url': 'https://weibo.cn/sinaurl/blockedafc34b21?from=1110006030&weiboauthoruid=1560906700&showurl=http%3A%2F%2Fmiaopai.com%2Fshow%2FdKC5AF-VVtYln1J9p%7EDsJjoB%7Eq5YaogfR5AyRw__.htm%3Ffrom%3D1110006030%26weiboauthoruid%3D1560906700&url_open_direct=1&toolbar_hidden=1&url_type=39&object_type=video&pos=2&containerid=2304426adf59d8bc630fe31011111012d56b44&luicode=10000011&lfid=1076031843242321&u=http%3A%2F%2Fmiaopai.com%2Fshow%2FdKC5AF-VVtYln1J9p%7EDsJjoB%7Eq5YaogfR5AyRw__.htm%3Ffrom%3D1110006030%26weiboauthoruid%3D1560906700%26showurl%3Dhttp%253A%252F%252Fmiaopai.com%252Fshow%252FdKC5AF-VVtYln1J9p%257EDsJjoB%257Eq5YaogfR5AyRw__.htm%253Ffrom%253D1110006030%2526weiboauthoruid%253D1560906700%26url_open_direct%3D1%26toolbar_hidden%3D1%26url_type%3D39%26object_type%3Dvideo%26pos%3D2%26containerid%3D2304426adf59d8bc630fe31011111012d56b44%26luicode%3D10000011%26lfid%3D1076031843242321', 'page_title': '阑夕的秒拍视频', 'content1': '阑夕的秒拍视频', 'content2': '多米诺骨牌爱好者的噩梦时刻 via@阑夕', 'type': 'video', 'media_info': {'stream_url': 'https://gslb.miaopai.com/stream/dKC5AF-VVtYln1J9p~DsJjoB~q5YaogfR5AyRw__.mp4?yx=&refer=weibo_app&Expires=1526922397&ssig=2WFjDJxp8i&KID=unistore,video'}, 'object_id': '2017607:6adf59d8bc630fe31011111012d56b44'}, 'bid': 'GhgCilj5a'}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 3, 'obj_ext': '505万次观看', 'raw_text': '[吃瓜]//@谷大白话:￼//@重工组长于彦舒:……真是太惨了…………//@御景零://@-河豚豚-: 顿时我都不难过了。。。这他妈太惨了', 'bid': 'GhmqEweLc'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4241013532277076', 'scheme': 'https://m.weibo.cn/status/GhcWR9yn2?mblogid=GhcWR9yn2&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-18', 'id': '4241013532277076', 'idstr': '4241013532277076', 'mid': '4241013532277076', 'can_edit': False, 'text': '今年的法来管前几年的事儿，看来“法无禁止则自由”也得慎重了，说不定哪天就找你“秋后算账”了，还真是魔幻现实主义<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_chigua-90cb948c34.png" style="width:1em;height:1em;" alt="[吃瓜]"></span> \u200b\u200b\u200b', 'textLength': 116, 'source': 'Weibo.intl', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 1, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 1, 'bid': 'GhcWR9yn2'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4240080878993537', 'scheme': 'https://m.weibo.cn/status/GgOGzBJD3?mblogid=GgOGzBJD3&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-15', 'id': '4240080878993537', 'idstr': '4240080878993537', 'mid': '4240080878993537', 'can_edit': False, 'text': 'bat脚本也是蛮可爱的<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_chigua-90cb948c34.png" style="width:1em;height:1em;" alt="[吃瓜]"></span> \u200b\u200b\u200b', 'textLength': 25, 'source': 'Weibo.intl', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 1, 'bid': 'GgOGzBJD3'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4235944380946705', 'scheme': 'https://m.weibo.cn/status/Gf54O3Yhr?mblogid=Gf54O3Yhr&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '05-04', 'id': '4235944380946705', 'idstr': '4235944380946705', 'mid': '4235944380946705', 'can_edit': False, 'text': '<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/others/d_miao-9ebe15b2c2.png" style="width:1em;height:1em;" alt="[喵喵]"></span>', 'source': '微博 weibo.com', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'retweeted_status': {'created_at': '05-04', 'id': '4235943076174276', 'idstr': '4235943076174276', 'mid': '4235943076174276', 'can_edit': False, 'text': '这就叫做天道好轮回吧。 <a data-url="http://t.cn/RumxC37" href="https://m.weibo.cn/p/index?containerid=230444aea03729fb9d29d56d39b061930abca5&url_type=39&object_type=video&pos=1&luicode=10000011&lfid=1076031843242321&ep=Gf52HpUd6%252C5851185687%252CGf52HpUd6%252C5851185687" data-hide=""><span class="url-icon"><img src="https://h5.sinaimg.cn/upload/2015/09/25/3/timeline_card_small_video_default.png"></span></i><span class="surl-text">电竞徐嘉诰的秒拍视频</a> \u200b\u200b\u200b', 'textLength': 42, 'source': 'OnePlus 5T', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 5851185687, 'screen_name': '电竞徐嘉诰', 'profile_image_url': 'https://tvax3.sinaimg.cn/crop.0.0.996.996.180/006nYYGHly8fdhinvmkz5j30ro0rotam.jpg', 'profile_url': 'https://m.weibo.cn/u/5851185687?uid=5851185687&luicode=10000011&lfid=1076031843242321', 'statuses_count': 754, 'verified': True, 'verified_type': 0, 'verified_type_ext': 1, 'verified_reason': '知名游戏博主', 'close_blue_v': False, 'description': '上海交通大学电竞社社长', 'gender': 'm', 'mbtype': 12, 'urank': 35, 'mbrank': 6, 'follow_me': False, 'following': False, 'followers_count': 503801, 'follow_count': 315, 'cover_image_phone': 'https://tva4.sinaimg.cn/crop.0.0.640.640.640/638f41a8jw1ewj858xp05j20hs0hs77s.jpg', 'avatar_hd': 'https://wx3.sinaimg.cn/orj480/006nYYGHly8fdhinvmkz5j30ro0rotam.jpg', 'like': False, 'like_me': False, 'badge': {'dzwbqlx_2016': 1, 'follow_whitelist_video': 1, 'super_star_2017': 1, 'user_name_certificate': 1, 'suishoupai_2018': 2, 'wenchuan_10th': 1, 'super_star_2018': 1}}, 'reposts_count': 26, 'comments_count': 40, 'attitudes_count': 56, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'cardid': 'star_021', 'content_auth': 0, 'edit_config': {'edited': False}, 'weibo_position': 2, 'page_info': {'page_pic': {'url': 'https://wx4.sinaimg.cn/orj480/006nYYGHly1fqz8g10qoij30lc0g00tk.jpg'}, 'page_url': 'https://m.weibo.cn/p/index?containerid=230444aea03729fb9d29d56d39b061930abca5&url_type=39&object_type=video&pos=2&luicode=10000011&lfid=1076031843242321', 'page_title': '电竞徐嘉诰的秒拍视频', 'content1': '电竞徐嘉诰的秒拍视频', 'content2': '这就叫做天道好轮回吧。', 'type': 'video', 'media_info': {'stream_url': 'https://f.us.sinaimg.cn/002WmnOFlx07kcg6rW8o01040200bfTy0k010.mp4?label=mp4_ld&template=480x360.27&Expires=1526922411&ssig=xcXGGLbWLj&KID=unistore,video'}, 'object_id': '1034:aea03729fb9d29d56d39b061930abca5'}, 'bid': 'Gf52HpUd6'}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 3, 'obj_ext': '2万次观看', 'raw_text': '[喵喵]', 'bid': 'Gf54O3Yhr'}, 'show_type': 0}
{'card_type': 9, 'itemid': '1076031843242321_-_4234111034030736', 'scheme': 'https://m.weibo.cn/status/GejnNgUzS?mblogid=GejnNgUzS&luicode=10000011&lfid=1076031843242321', 'mblog': {'created_at': '04-29', 'id': '4234111034030736', 'idstr': '4234111034030736', 'mid': '4234111034030736', 'can_edit': False, 'text': '<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/default/d_chigua-90cb948c34.png" style="width:1em;height:1em;" alt="[吃瓜]"></span>', 'source': 'Weibo.intl', 'favorited': False, 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 1843242321, 'screen_name': 'Helixcs', 'profile_image_url': 'https://tva3.sinaimg.cn/crop.8.0.291.291.180/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'profile_url': 'https://m.weibo.cn/u/1843242321?uid=1843242321&luicode=10000011&lfid=1076031843242321', 'statuses_count': 2765, 'verified': False, 'verified_type': -1, 'close_blue_v': False, 'description': 'Thread', 'gender': 'm', 'mbtype': 0, 'urank': 33, 'mbrank': 0, 'follow_me': False, 'following': False, 'followers_count': 98, 'follow_count': 567, 'cover_image_phone': 'https://tva1.sinaimg.cn/crop.0.0.640.640/549d0121tw1egm1kjly3jj20hs0hsq4f.jpg', 'avatar_hd': 'https://ww3.sinaimg.cn/orj480/6ddda551jw8f7zx0pjdkgj208c08c74m.jpg', 'like': False, 'like_me': False, 'badge': {'unread_pool': 1, 'unread_pool_ext': 1, 'dzwbqlx_2016': 1, 'user_name_certificate': 1}}, 'retweeted_status': {'created_at': '04-29', 'id': '4234104050556032', 'idstr': '4234104050556032', 'mid': '4234104050556032', 'can_edit': False, 'text': '小长假第一天，没人约没安排没心情没力气的你<span class="url-icon"><img src="//h5.sinaimg.cn/m/emoticon/icon/others/d_doge-d903433c82.png" style="width:1em;height:1em;" alt="[doge]"></span> \u200b\u200b\u200b', 'textLength': 48, 'source': '', 'favorited': False, 'thumbnail_pic': 'http://wx1.sinaimg.cn/thumbnail/c0788b86ly1fqtd8fwehaj20hm0d874x.jpg', 'bmiddle_pic': 'http://wx1.sinaimg.cn/bmiddle/c0788b86ly1fqtd8fwehaj20hm0d874x.jpg', 'original_pic': 'http://wx1.sinaimg.cn/large/c0788b86ly1fqtd8fwehaj20hm0d874x.jpg', 'is_paid': False, 'mblog_vip_type': 0, 'user': {'id': 3229125510, 'screen_name': '小野妹子学吐槽', 'profile_image_url': 'https://tva1.sinaimg.cn/crop.0.0.118.118.180/c0788b86jw8efz2k73zcmj203a03aglf.jpg', 'profile_url': 'https://m.weibo.cn/u/3229125510?uid=3229125510&luicode=10000011&lfid=1076031843242321', 'statuses_count': 17103, 'verified': True, 'verified_type': 0, 'verified_type_ext': 1, 'verified_reason': '微博知名博主', 'close_blue_v': False, 'description': '图文多转自日文推特，附以无责任吐槽。关注后易节操丧失、下限消亡、性向逆转、生理失调。', 'gender': 'm', 'mbtype': 12, 'urank': 48, 'mbrank': 7, 'follow_me': False, 'following': False, 'followers_count': 16510320, 'follow_count': 69, 'cover_image_phone': 'https://tva3.sinaimg.cn/crop.0.0.640.640.640/a1d3feabjw1ewdz1wa6lfj20hs0hsdkp.jpg', 'avatar_hd': 'https://ww1.sinaimg.cn/orj480/c0788b86jw8efz2k73zcmj203a03aglf.jpg', 'like': False, 'like_me': False, 'badge': {'gongyi': 1, 'bind_taobao': 1, 'dailv': 1, 'zongyiji': 1, 'dzwbqlx_2016': 1, 'follow_whitelist_video': 1, 'super_star_2017': 1, 'lol_gm_2017': 1, 'user_name_certificate': 1, 'suishoupai_2018': 4, 'wenchuan_10th': 1}}, 'picStatus': '0:1', 'reposts_count': 468, 'comments_count': 482, 'attitudes_count': 3111, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'weibo_position': 2, 'bid': 'Gejcx2kEg', 'pics': [{'pid': 'c0788b86ly1fqtd8fwehaj20hm0d874x', 'url': 'https://wx1.sinaimg.cn/orj360/c0788b86ly1fqtd8fwehaj20hm0d874x.jpg', 'size': 'orj360', 'geo': {'width': 359, 'height': 270, 'croped': False}, 'large': {'size': 'large', 'url': 'https://wx1.sinaimg.cn/large/c0788b86ly1fqtd8fwehaj20hm0d874x.jpg', 'geo': {'width': '634', 'height': '476', 'croped': False}}}]}, 'reposts_count': 0, 'comments_count': 0, 'attitudes_count': 0, 'pending_approval_count': 0, 'isLongText': False, 'visible': {'type': 0, 'list_id': 0}, 'more_info_type': 0, 'content_auth': 0, 'edit_config': {'edited': False}, 'mblogtype': 0, 'weibo_position': 3, 'raw_text': '[吃瓜]', 'bid': 'GejnNgUzS'}, 'show_type': 0}
.....

```

![img](https://raw.githubusercontent.com/Xarrow/weibo-scraper/master/weibo_tweets.png)

----
# P.S
1. Very Thanks For [Twitter-Scraper](https://github.com/kennethreitz/twitter-scraper)

2. Welcome to fork me .

----
# LICENSE

MIT
