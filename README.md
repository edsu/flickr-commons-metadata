# flickr-commons-metadata

flickr-commons-metadata contains the raw metadata for Flickr Commons photos in JSON format pulled from the Flickr API using the following methods:

* [flickr.photos.getInfo](http://www.flickr.com/services/api/flickr.photos.getInfo)
* [flickr.photos.getSizes](http://www.flickr.com/services/api/flickr.photos.getSizes)
* [flickr.photos.comments.getList](http://www.flickr.com/services/api/flickr.photos.comments.getList)
* [flickr.photos.getAllContexts](http://www.flickr.com/services/api/flickr.photos.getAllContexts)
* [flickr.photos.getExif](http://www.flickr.com/services/api/flickr.photos.getExif) _– if publicly available_

For example:

	$>ls -al data/83979593@N00/224/682/902/*
	-rw-r--r--  1 asc  staff    53 Dec 20 15:49 83979593@N00/224/682/902/224682902-c.json
	-rw-r--r--  1 asc  staff   255 Dec 20 15:49 83979593@N00/224/682/902/224682902-ctx.json
	-rw-r--r--  1 asc  staff  7952 Dec 20 15:49 83979593@N00/224/682/902/224682902-e.json
	-rw-r--r--  1 asc  staff  2273 Dec 20 15:49 83979593@N00/224/682/902/224682902-i.json
	-rw-r--r--  1 asc  staff  2060 Dec 20 15:49 83979593@N00/224/682/902/224682902-s.json

As of mid-morning December 21 (2013) metadata files contain a
`flarchive:created` attribute which is a Unix timestamp indicating when the file
was last archived.

For example:

	$> cat 6260452122-i.json | python -mjson.tool
	{
	    "flarchive:created": 1387636691, 
	    "photo": {
        	"comments": {
   	         "_content": "0"
        	}, 
	    ... and so on
	}

_That means as of mid-morning December 21 (2013) a bunch of metadata files
archived before this date are still missing the `flarchive:created` attribute._

## Details

Not all (read: most) participating institutions have been added to the
repository yet so contributions and pull requests are welcome.

Individual institutions are archived using the
[py-flarchive](https://github.com/straup/py-flarchive) library, like this:

	$> python ./flarchive/__init__.py -v -a <APIKEY> -n <NSID> -d flickr-commons-metadata/data

## Institutions

### In process

The following institutions are currently being archived by one or more people

* National Library of Sweden (hugovk / 20131223)
* Swedish National Heritage Board (hugovk / 20131223)
* Mississippi Department of Archives and History (straup / 20131223)
* The British Library (straup / 20131223)

_If you are archiving one or more institutions below add them here and send me a pull request or open an issue and I will add it to the list._

### Complete list

* [Musée McCord Museum](data/25786829%40N08) – _last archived 20131220_
* Cornell University Library	(30515687@N05)
* [National Maritime Museum](data/11334970%40N05) – _last archived 20131222_
* [Australian National Maritime Museum on The Commons](data/33147718%40N05) - _last archived 20131223_
* Texas State Archives	(47326604@N02)
* SMU Central University Libraries	(41131493@N06)
* nha.library	(34101160@N07)
* [Stockholm Transport Museum Commons](data/62173425%40N02) – _last archived 20131221_
* National Library of Ireland on The Commons	(47290943@N03)
* UL Digital Library	(95717549@N07)
* National Media Museum	(26808453@N03)
* UA Archives | Upper Arlington History	(37784107@N08)
* Getty Research Institute	(35532303@N08)
* [National Library of Sweden](data/95520404@N07) – _last archived 20131223_
* Center for Jewish History, NYC	(36988361@N08)
* [Smithsonian Institution](data/25053835%40N03) – _last archived 20131220_
* [The U.S. National Archives](data/35740357%40N03) – _last archived 20131222_
* OSU Special Collections & Archives : Commons	(34586311@N05)
* The Royal Library, Denmark	(45270502@N06) – _last archived 20131222_
* Mennonite Church USA Archives	(52529054@N06)
* The National Archives UK	(31575009@N05)
* Ljósmyndasafn Reykjavíkur / Reykjavík Museum of	(9189488@N02)
* [Brooklyn Museum](data/83979593%40N00) – _last archived 20131220_
* Keene and Cheshire County (NH) Historical Photos	(25960495@N06)
* The Field Museum Library	(35310696@N04)
* [National Galleries of Scotland Commons](data/30835311@N07) – _last archived 20131222_
* Jewish Historical Society of the Upper Midwest	(48143042@N05)
* [Het Nieuwe Instituut - Architecture Collection](data/47154409%40N06) – _last archived 20131221_
* [National Museum of Denmark](95772747%40N07) – _last archived 20131222_
* [National Library of Norway](data/48220291@N04) – _last archived 20131223_
* [Tyne & Wear Archives & Museums](data/29295370%40N07) - _last archived 20140116_
* Dundas Museum and Archives	(39758725@N03)
* Bergen Public Library	(37381115@N04)
* [National Library of Scotland](data/14456531@N07) – _last archived 20131222_
* [National Archives of Estonia](data/94021017@N05) – _last archived 20131222_
* [San Diego Air & Space Museum Archives](data/49487266%40N07) – _last archived 20140115_
* Museum of Hartlepool	(47908901@N03)
* [State Library and Archives of Florida](data/31846825%40N04) – _last archived 20131222_
* [LSE Library](data/35128489%40N07) – _last archived 20131223_
* Deseronto Archives	(23121382@N07)
* LlGC ~ NLW	(37199428@N06)
* [Swedish National Heritage Board](data/34419668@N08) – _last archived 20131223_
* Nova Scotia Archives	(61232251@N05)
* Public Record Office of Northern Ireland	(54403180@N04)
* The British Library	(12403504@N02)
* [Nationaal Archief](data/29998366%40N02) – _last archived 20131222_
* bibliothequedetoulouse	(26134435@N05)
* [California Historical Society Digital Collection](data/99278405%40N04) – _last archived 20131222_
* [Law Society of Upper Canada Archives](data/38561291%40N04) – _last archived 20131223_
* [Vancouver Public Library Historical Photographs](data/99915476%40N04) – _last archived 20131223_
* The Library of Virginia	(30194653@N06)
* [State Library of New South Wales collection](data/29454428%40N08) - _last 20140116_
* JWA Commons	(36281769@N04)
* [Costică Acsinte Archive](data/109550159%40N08) – _last archived 20131223_
* DEXTRA Photo	(88669438@N03)
* National Library of Australia Commons	(67193564@N03)
* Museum of Photographic Arts Collections	(61498590@N03)
* State Library of Queensland, Australia	(32605636@N06)
* [Biblioteca de Arte-Fundação Calouste Gulbenkian](data/26577438%40N06) – _last archived 20131222_
* [The Library of Congress](data/8623220%40N02) – _last archived 20131221_
* Royal Australian Historical Society	(69269002@N04)
* DC Public Library Commons	(36038586@N04)
* Fylkesarkivet i Sogn og Fjordane	(37547255@N08)
* [New York Public Library](data/32951986%40N05) – _last archived 20131221_
* [Riksarkivet (National Archives of Norway)](data/59811348@N05) – _last archived 20131223_
* Australian War Memorial collection	(30115723@N02)
* State Records NSW	(27331537@N06)
* UW Digital Collections	(8337233@N06)
* [George Eastman House](data/7167652%40N06) – _last archived 20131222_
* Schlesinger Library, RIAS, Harvard University	(99902797@N03)
* [NASA on The Commons](data/44494372%40N05) – _last archived 20131221_
* IWM Collections	(32300107@N06)
* Galt Museum & Archives on The Commons	(23686862@N03)
* [Svenska litteratursällskapet i Finland](data/48641766%40N05) – _last archived 20131221_
* Woodrow Wilson Presidential Library Archives	(41815917@N06)
* [Powerhouse Museum Collection](data/24785917%40N03) – _last archived 20131220_
* [Mississippi Department of Archives and History](data/77015680%40N05)  – _partially archived as of 20131223_
* [National Library NZ on The Commons](data/32741315%40N06) – _last archived 20131220_

## See also

* [py-flarchive](https://github.com/straup/py-flarchive)
