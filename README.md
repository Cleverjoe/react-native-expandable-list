# react-native-expandable-list

It is a expandableList component realized in react-native

# Two demos

![](http://oo819l870.bkt.clouddn.com/simple-list-demo.gif)
![](http://oo819l870.bkt.clouddn.com/qq-friend-list.gif)

# How to use

It is the simplest usage. For more details, u can see the two demos in src/pages/QQPage/FriendList.js or src/pages/SimpleListDemo/List.js.

```javascipt
const expandableListDemo = () => {

  data = [
    {
      groupHeaderData: {title: 'Dashboard'},
      groupListData: ['Calls', 'Chart', 'Map']
    },
    {
      groupHeaderData: {title: 'Profile'},
      groupListData: ['User', 'Add contact', 'Calendar']
    },
    {
      groupHeaderData: {title: 'Messages'},
      groupListData: ['Inbox', 'Sent', 'Deleted']
    },
    {
      groupHeaderData: {title: 'Settings'},
      groupListData: ['Fill Beer', 'Adjust', 'Alarm']
    }
  ];

  return (
    <ExpandableList
      data={data}
      renderGroupHeader={renderGroupHeader}
      renderGroupListItem={renderGroupListItem}
      />
  );

}

const renderGroupHeader = ({item, groupId, status, toggleStatus}) => {
  return (
    <TouchableWithoutFeedback onPress={toggleStatus}>
      <Text>{item.title}</Text>
    </TouchableWithoutFeedback>
  );
};

const renderGroupListItem = ({item, groupId, rowId}) => {
  return (
    <Text>
      {item}
    </Text>
  );
};
```

# More configs

|attr|value type|explanation|
|---|-----|----|
|data|array|the data of ExpandableList，each item in this array should contain groupHeaderData and groupListData|
|style|object|the style on expandableList|
|groupStyle|object|the style on each group item in expandableList|
|groupSpacing|number|the spacing between groups|
|implementedBy|string|expandableList supports 3 implementing method: View, ListView, FlatList(default)|
|renderGroupHeader({item, groupId, status, toggleStatus})|function|expandableList will use this function to render group header|
|renderGroupListItem({item, groupId, rowId})|function|expandableList will use this function to render each listItem|
|initialOpenGroups|array|when first rendering expandableList, it will open those groups whose index in the initialOpenGroups|
