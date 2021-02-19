### Installation global de GATSBY

```jsx
const mapStateToProps = (state) => ({
  createHotspotState: state.privateDB.hotspots.createHotspot,
});

const mapDispatchToProps = (dispatch, ownProps) => ({
  onSubmit: (data) =>
    dispatch(createHotspot({ privateDBId: ownProps.params.privateDBId, data })),
  onSuccess: (hotspotId) => {
    dispatch(
      openToast({ type: 'success', text: 'Hotspot changes have been saved.' })
    );
    dispatch(
      push(
        `/accounts/${ownProps.params.accountId}/privateDB/${ownProps.params.privateDBId}/hotspots/${hotspotId}`
      )
    );
  },
  onCancel: () => {
    dispatch(
      push(
        `/accounts/${ownProps.params.accountId}/privateDB/${ownProps.params.privateDBId}/hotspots`
      )
    );
  },
});

export default connect(mapStateToProps, mapDispatchToProps)(CreateHotspotPage);
```
